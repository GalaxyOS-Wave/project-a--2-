# Security Specification

## Data Invariants
1. Projects, Clients, and Invoices must be owned by the authenticated user (`owner_id` must match `request.auth.uid`).
2. Documents cannot be created without a valid `owner_id`.
3. `owner_id` cannot be modified after creation.

## The "Dirty Dozen" Payloads (Examples)
1. { "owner_id": "other_user_id", ... } (Trying to set another user's ID)
2. { "is_paid": true, ... } (Setting malicious fields if not authorized)
...

## Test Runner
(This section implies we should provide a test file if I were to run tests, but I will provide the rules based on the invariants).
