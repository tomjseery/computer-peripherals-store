# Computer Peripherals Store

A Java Swing retail application for browsing and managing a small computer-peripherals inventory. It provides separate customer and administrator workflows backed by flat-file product and account data.

## Features

### Customer workflow

- Login with a customer account
- Browse in-stock keyboards and mice
- Sort products by retail price
- Filter by brand and mouse-button count
- Add products to a basket and track the running total
- Simulate PayPal or card checkout
- Update stock after a completed purchase

### Administrator workflow

- View stock with wholesale and retail pricing
- Add new keyboards or mice
- Increase stock for an existing product
- Configure product-specific properties such as keyboard layout or mouse buttons
- Persist inventory changes to `Stock.txt`

## Running the application

The repository contains the original executable JAR. Run it from the repository root so it can locate the two data files:

```sh
java -jar store.jar
```

Example accounts from `UserAccounts.txt`:

| Role | ID | Username |
| --- | --- | --- |
| Administrator | `101` | `user1` |
| Customer | `102` | `user2` |

No password is used; these are demonstration records rather than real credentials.

## Data files

- `Stock.txt` stores keyboards and mice as comma-separated records.
- `UserAccounts.txt` stores account role, name and address data.
- The application expects both files in its current working directory.

## Design

The source models common product data in `Product`, with specialised `Keyboard` and `Mouse` subclasses. `Customer` and `Admin` extend the shared `User` model, while the two Swing menu classes implement their role-specific interfaces. `ProductReader` and `ProductWriter` provide the flat-file persistence layer.

## Status

This repository preserves an early object-oriented programming assignment. Payments are simulated, persistence is file-based and the checked-in JAR is the original build; it should be treated as a desktop demonstration rather than a production retail system.
