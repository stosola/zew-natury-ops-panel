# Zew Natury - Ops Panel

| | |
|---|---|
| Version | 1.0.0 |
| Owner | Zew Natury (Allegro seller account: zew-natury) |
| Platform | Allegro REST API |
| Auth | OAuth 2.0 Device Flow |
| Access | read-only |
| Status | internal tool |

Internal dashboard of Zew Natury, a shop selling dog and cat food. We use it to follow sales, costs, offer performance, ratings and order handling on Allegro. It works with our own seller account only and is not offered to other sellers.

## Documentation

- [Application details](docs/zew-natury-ops-panel.md) - what the app reads, how often, how credentials are kept

## Scope

The panel combines Allegro data with our own sales data: offer stats, product and seller ratings, sales quality, Allegro fees, order and shipment status. It shows what needs attention, for example delayed parcels, low stock or a drop in ratings. It does not create or change anything on Allegro.

## This repository

Documentation only. Source code, credentials, tokens and any customer or sales data stay on our side and are never committed here.
