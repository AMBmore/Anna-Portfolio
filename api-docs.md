---
title: API Documentation
layout: default
parent: Technical Writing Samples
nav_order: 1
---

# Fantasy Library API

## Overview

The Fantasy Library API allows developers to manage digital and physical library workflows through a REST-based interface. This sample endpoint demonstrates how users can create and manage book checkout records programmatically.

This documentation sample was created as part of a technical writing portfolio project to demonstrate API documentation structure, developer-focused writing, and information architecture using Markdown and GitHub Pages.

[Add additional introductory context here about the project, goals, or fictional company background.]

---

## Audience and Purpose

This documentation is intended for:

- Front-end developers integrating checkout functionality
- Back-end developers managing lending workflows
- QA testers validating API behavior
- Technical stakeholders reviewing API functionality

The purpose of this document is to provide clear implementation guidance for interacting with the checkout endpoint while demonstrating professional API documentation standards.

[Add more audience or use-case details here if desired.]

---

# Create a Checkout

**POST** `/v1/library/checkouts`

Creates a new checkout record for a library book.

This endpoint supports both physical and ebook lending workflows and automatically applies checkout policies such as due dates, borrowing restrictions, and user account validation.

---

## Authentication

Requests must include a valid API key using Bearer authentication.

```http
Authorization: Bearer sk_test_...
```

---

## Request Parameters

All parameters are sent as `application/x-www-form-urlencoded`.

| Parameter       | Type    | Required | Description                                 |
| --------------- | ------- | -------- | ------------------------------------------- |
| `user`          | string  | Yes      | ID of the user checking out the book        |
| `book`          | string  | Yes      | ID of the book to check out                 |
| `due_days`      | integer | No       | Number of days until due (default: 14)      |
| `format`        | enum    | No       | `physical` or `ebook` (default: `physical`) |
| `pickup_branch` | string  | No       | Required if `format=physical`               |
| `metadata`      | object  | No       | Key-value pairs for additional info         |

### Implementation Notes

- Physical books require a valid pickup branch.
- Ebook checkouts become immediately available after request completion.
- If `due_days` is omitted, the system automatically applies the default lending period.

[Add additional implementation notes or business rules here.]

---

## Example Request

```bash
curl https://api.fantasy-library.io/v1/library/checkouts \
  -u sk_test_123: \
  -d user=user_789 \
  -d book=book_456 \
  -d due_days=21 \
  -d format=physical \
  -d pickup_branch=branch_west_tower
```

---

## Example Response

Successful requests return a `library.checkout` object.

```json
{
  "id": "chk_1NwZQ2Lxk9s8",
  "object": "library.checkout",
  "created": 1712352000,
  "livemode": false,
  "user": "user_789",
  "book": "book_456",
  "status": "checked_out",
  "format": "physical",
  "due_date": 1714166400,
  "pickup_branch": "branch_west_tower",
  "metadata": {}
}
```

---

## Checkout Object

| Attribute       | Type        | Description                                    |
| --------------- | ----------- | ---------------------------------------------- |
| `id`            | string      | Unique identifier for the checkout (`chk_...`) |
| `object`        | string      | Always `"library.checkout"`                    |
| `created`       | timestamp   | Unix timestamp of object creation              |
| `livemode`      | boolean     | Indicates whether the object exists in live mode |
| `user`          | string      | ID of the user                                 |
| `book`          | string      | ID of the book                                 |
| `status`        | string      | `checked_out`, `returned`, or `overdue`        |
| `format`        | string      | `physical` or `ebook`                          |
| `due_date`      | timestamp   | Scheduled due date                             |
| `pickup_branch` | string/null | Pickup location                                |
| `metadata`      | object      | Arbitrary key-value data                       |

---

## Idempotency

This endpoint supports idempotency keys to safely retry requests without creating duplicate checkout records.

```http
Idempotency-Key: chk_abc123_unique_key
```

Idempotency is especially useful in situations involving network interruptions or repeated client requests.

---

## Expandable Fields

Certain fields can be expanded using the `expand` parameter.

| Field  | Description                 |
| ------ | --------------------------- |
| `user` | Expands to full user object |
| `book` | Expands to full book object |

### Example

```bash
-d "expand[]=user" \
-d "expand[]=book"
```

---

## Error Handling

The API uses a Stripe-style error format to provide consistent error reporting.

```json
{
  "error": {
    "type": "invalid_request_error",
    "message": "The book is already checked out.",
    "param": "book",
    "code": "book_unavailable"
  }
}
```

### Common Error Scenarios

| Error Code            | Description                         |
| --------------------- | ----------------------------------- |
| `book_unavailable`    | Book is already checked out         |
| `user_limit_reached`  | User exceeded active checkout limit |
| `invalid_branch`      | Pickup branch does not exist        |

[Add additional error scenarios or troubleshooting information here.]

---

## Checkout Rules and Behavior

The system automatically applies the following lending policies:

- Users can have up to **10 active checkouts**
- Restricted books require elevated permissions
- Overdue accounts may be temporarily blocked from creating new checkouts
- Ebook checkouts do not require pickup locations

---

## Related Endpoints

| Method | Endpoint                            | Description         |
| ------ | ----------------------------------- | ------------------- |
| `GET`  | `/v1/library/checkouts/{id}`        | Retrieve a checkout |
| `POST` | `/v1/library/checkouts/{id}/return` | Return a book       |
| `GET`  | `/v1/library/checkouts`             | List all checkouts  |

---

## Tools Used

This documentation sample was created using:

- Markdown
- GitHub Pages
- Jekyll
- REST API documentation conventions
- Command-line request examples using cURL

[Add additional tools, frameworks, or workflow details here.]

---

## Technical Writing Notes

This portfolio sample was designed to demonstrate:

- API endpoint documentation
- Information hierarchy and readability
- Structured request and response formatting
- Error handling documentation
- Developer-focused writing
- Markdown documentation workflows

[Add personal reflections, writing decisions, or lessons learned here.]
