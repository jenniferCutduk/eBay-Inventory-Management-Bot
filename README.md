# eBay Inventory Management Bot

> A production-ready Android automation that keeps your eBay listings in sync — auto-updates quantities, prices, and item statuses across accounts and devices. It replaces manual stock edits with a resilient workflow that reads inventory sources, updates the eBay app or web, and verifies changes with logs and screenshots. The result: fewer oversells, faster response to demand, and a stable seller rating powered by reliable inventory handling.

<p align="center">
  <a href="https://Appilot.app" target="_blank"><img src="media/appilot-baner.png" alt="Appilot Banner" width="100%"></a>
</p>
<p align="center">
 <a href="https://t.me/devpilot1" target="_blank"><img src="https://img.shields.io/badge/Chat%20on-Telegram-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white" alt="Telegram"></a>
 <a href="mailto:support@appilot.app" target="_blank"><img src="https://img.shields.io/badge/Email-support@appilot.app-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Gmail"></a>
 <a href="https://appilot.app" target="_blank"><img src="https://img.shields.io/badge/Visit-Website-007BFF?style=for-the-badge&logo=google-chrome&logoColor=white" alt="Website"></a>
 <a href="https://discord.gg/r5sJ5vhf" target="_blank"><img src="https://img.shields.io/badge/Join-Appilot_Community-5865F2?style=for-the-badge&logo=discord&logoColor=white" alt="Appilot Discord"></a>
</p>

<p align="center"> 
   Created by Appilot, built to showcase our approach to Automation!<br>
   <strong>If you are looking for custom eBay Inventory Management Bot, you've just found your team — Let’s Chat.👆👆</strong>
</p>

## Introduction
This system automates every repetitive step of eBay stock control on Android—checking current quantities, applying price rules, pausing out-of-stock items, and reactivating replenished SKUs. It removes platform-hopping and error-prone typing, giving teams a single, consistent workflow. Businesses gain real-time control of their catalog, cleaner seller metrics, and a scalable foundation for multi-store operations.

### Automating eBay Stock, Price & Status Updates

* Fully headless or on-device execution that reads inventory from CSV/API/DB and applies updates to the eBay app or mobile web.
* Built-in price/quantity rules (min/max, MAP, margin floors) with safe-guards to prevent accidental zeroing or price drops.
* Robust anti-detection behaviors: human-like delays, randomization, and UI adaptation for different device resolutions.
* End-to-end observability with structured logs, screenshot evidence, and per-SKU execution receipts.
* Parallel device scaling for bulk catalogs and multi-account sellers.

## Core Features

* **Real Devices and Emulators:** Run on physical phones/tablets or emulators (Bluestacks/Nox). Handles different screen DPIs and OEM skins reliably.
* **No-ADB Wireless Automation:** Operates via Accessibility/UI Automator paths with optional on-device agents—no cable or ADB pairing required after enrollment.
* **Mimicking Human Behavior:** Randomized tap paths, scroll inertia, think-times, and typo-corrections to emulate natural usage patterns.
* **Multiple Accounts Support:** Account context switching with isolated cookies/sessions, per-store rules, and role-based credentials.
* **Multi-Device Integration:** Dispatch tasks across a device farm; queue and shard SKUs by store, price band, or urgency.
* **Exponential Growth for Your Account:** Always-in-stock listings + responsive repricing improve search rank, conversion, and seller KPIs.
* **Premium Support:** Priority incident response, runbook customization, and CI-friendly updates.
* **Rule-Based Repricing:** Margin/momentum rules (competitor delta, inventory age) with floors/ceilings and audit trails.
* **Smart OOS Handling:** Auto-pause OOS items, auto-relist on replenishment, and backorder/lead-time labels.

| Feature                 | Description                                                                                                        |
| ----------------------- | ------------------------------------------------------------------------------------------------------------------ |
| **SKU Mapping Engine**  | Connects marketplace titles/variations to internal SKUs; resolves duplicates and variation children automatically. |
| **Data Connectors**     | Import/export via CSV, Google Sheets, REST API, or DB (MySQL/Postgres). Schedules syncs and validates schema.      |
| **Scheduler & Queue**   | Cron-like schedules with priority queues; retries with exponential backoff and dead-letter handling.               |
| **Proxy & IP Rotation** | Per-account proxy pools and location pinning to align with account region/trust patterns.                          |
| **Visual Checks & OCR** | Screenshot + OCR validation of on-screen quantities/prices for closed-loop verification.                           |
| **Alerting & Webhooks** | Slack/Discord/email notifications for failures, threshold breaches, or rule-driven events.                         |

</p>
<p align="center">
  <a href="https://appilot.app" target="_blank">
    <img src="media/ebay-inventory-management-bot-banner.png" alt="ebay-inventory-management-bot-architecture" width="95%">
  </a>
</p>

## How It Works

1. **Input or Trigger** — Trigger from the Appilot dashboard by selecting a store/account, choosing the inventory source (CSV/API/DB), and defining rules (repricing, OOS actions, relist thresholds).
2. **Core Logic** — The bot controls an Android device/emulator using UI Automator (or Accessibility) to open the eBay app/web, navigate to listings, and apply quantity/price/status changes. ADB is optional and not required in wireless mode.
3. **Output or Action** — Listings are updated; the system captures screenshots and structured logs, then emits a per-SKU report and optional webhooks to your ERP or Slack.
4. **Other functionalities** — Automatic retries, error classification (UI drift, network, credential), device health checks, and parallel processing are managed from the Appilot dashboard with run-time overrides.

## Tech Stack

* **Language:** Kotlin, Java, Python, JavaScript
* **Frameworks:** Appium, UI Automator, Espresso, Robot Framework, Cucumber
* **Tools:** Appilot, Android Debug Bridge (ADB), Appium Inspector, Bluestacks, Nox Player, Scrcpy, Firebase Test Lab, MonkeyRunner, Accessibility
* **Infrastructure:** Dockerized device farms, Cloud-based emulators, Proxy networks, Parallel Device Execution, Task Queues, Real device farm

## Directory Structure

```
    ebay-inventory-management-bot/
    │
    ├── src/
    │   ├── main.py
    │   ├── automation/
    │   │   ├── device_controller.py
    │   │   ├── ebay_flows.py
    │   │   ├── rules_engine.py
    │   │   ├── ocr_validator.py
    │   │   └── utils/
    │   │       ├── logger.py
    │   │       ├── proxy_manager.py
    │   │       ├── config_loader.py
    │   │       └── retry.py
    │   ├── connectors/
    │   │   ├── csv_loader.py
    │   │   ├── sheets_client.py
    │   │   ├── rest_api_client.py
    │   │   └── db_client.py
    │   └── dashboard/
    │       ├── api.py
    │       └── webhooks.py
    │
    ├── config/
    │   ├── settings.yaml
    │   ├── credentials.env
    │   └── devices.yaml
    │
    ├── tests/
    │   ├── test_rules_engine.py
    │   ├── test_sku_mapping.py
    │   └── fixtures/
    │       └── sample_inventory.csv
    │
    ├── scripts/
    │   ├── enroll_device.sh
    │   ├── run_scheduler.sh
    │   └── export_reports.py
    │
    ├── logs/
    │   ├── runs/
    │   └── device_health.log
    │
    ├── output/
    │   ├── reports/
    │   │   ├── run_YYYYMMDD.json
    │   │   └── run_YYYYMMDD.csv
    │   └── screenshots/
    │
    ├── docker/
    │   ├── Dockerfile
    │   └── docker-compose.yaml
    │
    ├── requirements.txt
    └── README.md
```

## Use Cases

* **SMB sellers** use it to synchronize stock and prices daily across multiple stores, so they prevent oversells and keep margins healthy.
* **Aggregators/Agencies** use it to manage dozens of seller accounts at scale, so they standardize rules and reporting without hiring extra staff.
* **Ops teams** use it to auto-pause OOS listings and relist on replenishment, so they maintain visibility and protect seller ratings.
* **Developers** integrate it via webhooks and APIs, so they push inventory updates from ERP/WMS directly to Android device farms.

## FAQs

**How do I configure this automation for multiple accounts?**
Create account profiles in `config/settings.yaml`, assign proxies and credentials per profile, and define per-account rules in the dashboard. The scheduler shards SKUs by account to avoid cross-session leakage.

**Does it support proxy rotation or anti-detection?**
Yes. Per-account proxy pinning or rotation is supported. Interaction randomization (gesture speed, offsets, scroll variance) and UI path fallbacks reduce repeatable fingerprints.

**Can I schedule it to run periodically?**
Absolutely. Use the built-in scheduler to run hourly/daily/weekly jobs. Jobs can be paused, resumed, and prioritized; missed runs are re-queued with backoff.

**What happens if the UI changes?**
Fallback selectors and visual anchors (OCR/text checks) kick in. If both fail, the task retries with alternative flows and raises an alert with screenshots for quick rule updates.

## Performance & Reliability Benchmarks

* **Execution Speed:** ~800–1,500 SKU updates per hour per device, depending on UI path and network conditions.
* **Success Rate:** **95%** end-to-end on stable UI builds with proper selectors and proxies.
* **Scalability:** Horizontal scale to **300–1,000** Android devices via device farms and shardable queues; linear throughput gains observed.
* **Resource Efficiency:** Lightweight workers (<300MB RAM per headless emulator); image capture and OCR are batched to minimize overhead.
* **Error Handling:** Categorized retries (transient vs. persistent), circuit breakers for repeated UI drift, structured logs, screenshot trails, and Slack/Discord alerts for human-in-the-loop review.

##
<p align="center">
<a href="https://cal.com/app-pilot-m8i8oo/30min" target="_blank">
  <img src="https://img.shields.io/badge/Book%20a%20Call%20with%20Us-34A853?style=for-the-badge&logo=googlecalendar&logoColor=white" alt="Book a Call">
</a>
</p>
