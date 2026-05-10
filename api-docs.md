---
title: API Documentation
layout: default
parent: Technical Writing Samples
nav_order: 1
---

# Fantasy Library API

## Overview

The Fantasy Library API is a fictional REST-based service designed to simulate modern library management systems that support both physical and digital lending workflows. It enables developers to manage core operations such as user accounts, book checkouts, and lending policies programmatically.

Fantasy Library is a fictional cloud-based platform built for public libraries, academic institutions, and regional lending networks. It supports media circulation, branch coordination, and automated lending workflows across distributed systems.

This documentation sample was developed as part of my technical writing portfolio to demonstrate API documentation structure, information architecture, and developer-focused writing using Markdown and GitHub Pages. Prompt engineering techniques and AI-assisted tools such as ChatGPT and Claude Code were used to model a realistic API workflow and incorporate real-world constraints commonly found in library systems.

---

## Audience

This documentation is intended for:

- Front-end developers building user-facing library applications  
- Back-end developers implementing lending and catalog systems  
- QA engineers validating API behavior and error handling  
- Technical reviewers assessing system design and integration patterns  

The purpose of this document is to provide clear implementation guidance for interacting with the checkout endpoint while demonstrating professional API documentation standards. The API is designed to be predictable, consistent, and easy to integrate into modern web and mobile applications.

---

## Scope

This documentation focuses specifically on the checkout workflow within the Fantasy Library API. It covers request structure, authentication, response formatting, error handling, and related lending behavior.

Additional system functionality such as catalog search, user authentication, and inventory management is referenced but not included in this section.

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
- Ebook availability is subject to licensing agreements and may limit concurrent checkouts across institutions.
- If `due_days` is omitted, the system automatically applies the default lending period.  
- If multiple checkout requests are submitted simultaneously for the same book, only the first successful transaction will be committed. Subsequent requests will return a `book_unavailable` error.
- Due dates are automatically adjusted to avoid statutory holidays and institutional closure periods.
- Accounts with repeated overdue activity may be flagged for review and temporarily restricted from new checkouts.

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
- Claude Code
- VS Code

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
