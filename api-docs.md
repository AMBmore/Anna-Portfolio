---
title: API Documentation
layout: default
parent: Technical Writing Samples
nav_order: 1
---

# Fantasy Library API

## Overview

The Fantasy Library API is a fictional REST-based service designed to simulate modern library management systems that support both physical and digital lending workflows. It enables developers to manage core operations such as user accounts, book checkouts, and lending policies.

Fantasy Library is a fictional cloud-based platform built for public libraries, academic institutions, and regional lending networks. It supports media circulation, branch coordination, and automated lending workflows across distributed systems.

This documentation sample was developed as part of my technical writing portfolio to demonstrate API documentation structure, information architecture, and developer-focused writing using Markdown and GitHub Pages. Prompt engineering techniques and AI-assisted tools such as ChatGPT and Claude Code were used to model a realistic API workflow and incorporate real-world constraints commonly found in library systems.

---

## Audience and Purpose

This documentation is intended for:

- Front-end developers building user-facing library applications  
- Back-end developers implementing lending and catalog systems  
- QA engineers validating API behavior and error handling  
- Technical reviewers assessing system design and integration patterns  

The purpose of this document is to provide clear implementation guidance for interacting with the checkout endpoint while demonstrating professional API documentation standards. The API is designed to be predictable, consistent, and easy to integrate into modern web and mobile applications.

---

## Scope

This documentation focuses on the checkout workflow within the Fantasy Library API, including authentication, request and response structure, error handling, and related lending behavior.

Additional functionality such as catalog search, user authentication, and inventory management is referenced but not covered in this section. Some system-level behaviors are included where they directly affect checkout processing.

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

- Physical books require a valid pickup branch
- If `format=ebook`, the `pickup_branch` field is ignored
- If `due_days` is omitted, the system automatically applies the default lending period  
- Simultaneous requests for the same resource are processed sequentially to prevent duplicate checkouts
- Parameter names are case-sensitive
- Metadata keys are limited to 40 characters and values are limited to 500 characters
- Requests sent with invalid content types will return an `unsupported_media_type` error

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

| Error Code            | Description                                       |
| --------------------- | ------------------------------------------------- |
| `book_unavailable`    | Book is already checked out                       |
| `user_limit_reached`  | User exceeded active checkout limit (10)          |
| `invalid_branch`      | Pickup branch does not exist                      |
| `restricted_item`     | book requires administrative approval             |
| `missing_parameter`   | required field not provided (e.g., `user`, `book`)|

---

## Checkout Rules and Behavior

The system automatically applies the following lending policies:

- Users can have up to **10 active checkouts**
- Restricted books require elevated permissions
- Ebook availability is subject to licensing agreements and may limit concurrent checkouts across institutions
- Overdue accounts may be temporarily blocked from creating new checkouts
- Ebook checkouts do not require pickup locations
- Accounts with repeated overdue activity may be flagged for review and temporarily restricted from new checkouts
- Due dates are automatically adjusted to avoid statutory holidays and institutional closure periods

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

---

## Technical Writing Notes

This documentation sample was designed to emulate production-level API documentation commonly found in developer platforms such as Stripe and GitHub. One of the primary writing decisions was to structure the documentation in a modular format (Overview → Authentication → Request → Response → Errors). This approach was chosen to support quick scanning and predictable navigation patterns, which are critical in developer-facing documentation.

Another intentional decision was to include realistic constraints such as rate limiting, idempotency, and branch-level policy differences. These additions were used to reflect real-world system complexity rather than presenting an overly simplified API model.

Using AI-assisted tools such as ChatGPT and Claude Code helped accelerate the drafting process and allowed for rapid creation of edge cases and error scenarios. However, all structural decisions, documentation architecture, and final wording were reviewed and refined manually to ensure clarity and consistency.

### Lessons Learned

- Clear separation between “how to use” and “system behavior” improves usability  
- Adding realistic failure scenarios makes documentation more credible and useful for developers  
- Consistent formatting across tables, code blocks, and sections is essential for readability  
- API documentation benefits greatly from thinking in terms of developer tasks rather than just endpoints  

### Future Improvements

In the future, I would expand this documentation to include additional endpoints such as user authentication and catalog search, to better represent a full API ecosystem. I would also incorporate interactive examples to further enhance usability.

