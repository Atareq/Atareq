# Ahmed Tarek

**Backend Software Engineer** · Cairo, Egypt

[LinkedIn](https://www.linkedin.com/in/ahmed-tarek-b29283243/) ·
[tarekahmad8509@gmail.com](mailto:tarekahmad8509@gmail.com) ·
+20 100 282 8648

I build Python and Django backends where correctness matters: bookings that
must not be sold twice, money that must reconcile, and stock that must not go
negative. I work at **[ShipBlu](https://shipblu.com)**, an Egyptian e-commerce
logistics company that runs last-mile delivery and fulfillment centers.

## Core expertise

- REST API design with Django and Django REST Framework, including role- and
  scope-based authorization
- PostgreSQL transactions, row locking, constraints and query performance
- Background processing with Celery and Redis, and idempotent side effects
- Testing with pytest, including concurrency tests against real PostgreSQL
- CI/CD with GitHub Actions, Docker and systemd deployments, and AWS

## Experience: ShipBlu

195+ merged pull requests to the core backend (Django REST Framework,
PostgreSQL, Celery, AWS), including:

- **Shopify marketplace:** API client, cart, multi-store checkout, and order
  sync between merchants' Shopify stores and ShipBlu's fulfillment network.
- **Expiry-aware inventory:** expiry-dated stock batches, storage units that
  hold one SKU and one expiry date, and FEFO (first-expiry, first-out)
  allocation for outbound orders and stock recalls.
- **Merchant money flows:** automated instant payouts, exchange-order pricing,
  and safeguards for orders with missing shipping prices.
- **Delivery operations:** OTP-verified return refunds, structured delivery
  failure reasons, hourly shipment exports, and a WhatsApp relay with chat
  history on DynamoDB.

## Flagship projects

### Sloty: sports court booking platform

[API](https://github.com/Atareq/sloty-backend) ·
[Web app](https://github.com/Atareq/sloty-frontend)

A Django REST API and an Arabic-first React PWA for clubs that rent courts by
the hour and collect cash at the desk.

- Prevents double bookings by locking the court row and re-checking overlaps
  inside the same transaction.
- Makes retries after a dropped connection safe, with per-club idempotency
  keys for bookings and payments.
- Proves both with 15 thread-based tests that run against PostgreSQL
  ([tests](https://github.com/Atareq/sloty-backend/blob/dev/tests/test_postgresql_concurrency.py)).
- Tracks staff cash custody through to settlement under a written
  [financial consistency contract](https://github.com/Atareq/sloty-backend/blob/dev/docs/financial-consistency-contract.txt).

### PPW: pigeon auction and marketplace backend

[Repository](https://github.com/Atareq/PPW)

Auctions, a supplies marketplace, manual payment approval and real-time
notifications across 25 Django apps, deployed with Docker Compose.

- Re-validates every bid under a row lock on the auction item.
- Closes expired auctions idempotently from Celery Beat.
- Runs notifications and rewards in `on_commit` hooks with idempotency keys.

### Colorectal cancer risk prediction

[Repository](https://github.com/Atareq/Graduation-Project-Detecting-colorectal-cancer)

Graduation project: a Django app that scores patients' clinical data with a
scikit-learn model.

I have also built backends for a multi-tenant authentication service, a
delivery management system and an e-commerce platform as part of freelance
teams.

## Technologies

Python · Django · Django REST Framework · PostgreSQL · Redis · Celery ·
Django Channels · Docker · GitHub Actions · AWS · pytest · TypeScript · React
