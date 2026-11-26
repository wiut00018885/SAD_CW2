# Safia Branch Management System – high-fidelity prototype

Coursework 2 (individual), 6BUIS026C Systems Analysis and Design, Westminster International University in Tashkent.
Student ID: **[YOUR STUDENT ID]**

This repository holds the executable high-fidelity prototype described in section 1.2 of the report.

> Coursework prototype with invented demo data. It is not an official Safia system.

## The prototype file

| File | What it is |
|---|---|
| `index.html` | The whole prototype: HTML, CSS and JavaScript in one file |

Design files referred to in the report are in `docs/` (open them at app.diagrams.net):

| File | What it is |
|---|---|
| `docs/Safia_LowFi_Prototype.drawio` | Low-fidelity prototype: navigation map, board and 20 linked screens |
| `docs/Safia_UML_Diagrams.drawio` | Architecture diagram and three class diagrams |
| `docs/Safia_Methodology.drawio` | Diagram of the proposed development methodology |

## How to run it

1. Download `index.html`.
2. Open it in a browser (Chrome, Edge, Firefox or Safari). No server and no installation are needed.

An internet connection is only used to load two web fonts; the prototype works without it.

## Demo accounts

Choose a branch on the login page, then log in or use the one-click role cards.

| Branch | Sales assistant | Branch manager |
|---|---|---|
| Vega branch | 1001 / 1234 | 2001 / 4321 |
| Chilanzar branch | 1002 / 1234 | 2002 / 4321 |
| Yunusabad branch | 1003 / 1234 | 2003 / 4321 |

Other branches follow the same pattern (the login card shows the accounts of the selected branch). The manager PIN for write-off approval is 4321.

## What it demonstrates

| Function | Use case |
|---|---|
| Counter sale: scan or search, basket, cash / card / QR payment, receipt, stock deduction after payment, low-stock alert | UC-02 |
| Custom cake order: customer lookup, structured details, date and capacity check, read-back, deposit, order number and SMS | UC-01 |
| Order register: search, filter by status, move an order through its statuses | UC-01 |
| Delivery handover: verify courier by order number, five refusal reasons, item checklist | UC-03 |
| Closing stock: count, reasons for differences and write-offs, manager approval by PIN, closing report | UC-04 |
| Manager dashboard and replenishment request | Reports |
| Branch selection, per-branch stock, staff, opening hours, payment methods and write-off limit | NFR-05 |
| Offline switch: outgoing messages are queued and sent when back online | NFR-02 |

"Demo control" tick boxes on the payment screens make the next card payment fail, so the exception paths can be shown.

## Code structure

The JavaScript classes in `index.html` use the names from the UML class diagrams in the report.

| Package | Classes |
|---|---|
| staff | `Branch`, `Employee`, `SalesAssistant`, `BranchManager` |
| inventory | `Product`, `StockItem`, `StockCount`, `ReplenishmentRequest` |
| pos | `Sale`, `SaleLine`, `Payment`, `CashPayment`, `CardPayment`, `QrPayment` |
| orders | `CustomOrder`, `CakeDesign`, `Customer`, `ProductionSlot`, `ProductionSchedule`, `DepositPolicy`, `OrderStatus` |
| delivery | `DeliveryOrder`, `HandoverVerifier` |
| reporting | `SalesReport`, `ClosingReport` |
| integration | `Outbox`, `SmsNotifier`, `CardTerminalAdapter`, `YandexAdapter`, `SafiaAppAdapter` |

## Limits

- All data is held in memory and resets when the page is reloaded.
- Branches other than Vega, and all staff, products, prices, customers and orders, are invented.
- The card terminal, SMS gateway, delivery platforms and production are simulated; their messages appear in the Messages panel.

## Use of AI

The prototype code was produced with an AI coding agent (Claude), as the coursework brief permits for the high-fidelity prototype.
