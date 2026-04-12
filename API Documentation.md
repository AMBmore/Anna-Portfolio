---
title: API Documentation
layout: default
parent: Technical Writing Samples
nav_order: 1
---

# API Documentation

# Fantasy Library API

## Create a Checkout

**POST /v1/library/checkouts**

Creates a new checkout for a library book.

---

## Authentication

```http
Authorization: Bearer sk_test_...
| Parameter     | Type    | Required | Description                            |
| ------------- | ------- | -------- | -------------------------------------- |
| user          | string  | Yes      | ID of the user checking out the book   |
| book          | string  | Yes      | ID of the book to check out            |
| due_days      | integer | No       | Number of days until due (default: 14) |
| format        | enum    | No       | physical or ebook (default: physical)  |
| pickup_branch | string  | No       | Required if format=physical            |
| metadata      | object  | No       | Key-value pairs for additional info    |

curl https://api.fantasy-library.io/v1/library/checkouts \
  -u sk_test_123: \
  -d user=user_789 \
  -d book=book_456 \
  -d due_days=21 \
  -d format=physical \
  -d pickup_branch=branch_west_tower

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

| Attribute     | Type        | Description                                  |
| ------------- | ----------- | -------------------------------------------- |
| id            | string      | Unique identifier for the checkout (chk_...) |
| object        | string      | Always "library.checkout"                    |
| created       | timestamp   | Time of creation                             |
| livemode      | boolean     | Whether object exists in live mode           |
| user          | string      | ID of the user                               |
| book          | string      | ID of the book                               |
| status        | string      | checked_out, returned, overdue               |
| format        | string      | physical or ebook                            |
| due_date      | timestamp   | When the book is due                         |
| pickup_branch | string/null | Pickup location                              |
| metadata      | object      | Arbitrary key-value data                     |

Idempotency-Key: chk_abc123_unique_key

| Field | Description                 |
| ----- | --------------------------- |
| user  | Expands to full user object |
| book  | Expands to full book object |

-d "expand[]=user" \
-d "expand[]=book"

{
  "error": {
    "type": "invalid_request_error",
    "message": "The book is already checked out.",
    "param": "book",
    "code": "book_unavailable"
  }
}

- Users can have up to 10 active checkouts
- Books marked as "restricted" cannot be checked out without special permission
- Overdue users may receive errors when attempting new checkouts

| Method | Endpoint                          | Description         |
| ------ | --------------------------------- | ------------------- |
| GET    | /v1/library/checkouts/{id}        | Retrieve a checkout |
| POST   | /v1/library/checkouts/{id}/return | Return a book       |
| GET    | /v1/library/checkouts             | List all checkouts  |

