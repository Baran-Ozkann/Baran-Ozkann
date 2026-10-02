# Baran Özkan

Software Engineering student (3rd year) focused on **backend systems** — Java 21, Spring Boot, PostgreSQL, Kafka — with Python for data and ML work.

I'm drawn to problems where "the tests pass" isn't good enough: concurrency, idempotency, money that has to add up. Before I call something correct, I try to break it — remove each safeguard on purpose to confirm a test catches it, load-test until it saturates, and write down exactly where it stops.

[LinkedIn](https://www.linkedin.com/in/baranozkan1) · [ozkanbarran@gmail.com](mailto:ozkanbarran@gmail.com)

---

## Featured work

### [ledger-payment-core](https://github.com/Baran-Ozkann/ledger-payment-core)
`Java 21` `Spring Boot` `PostgreSQL` `Kafka` `Testcontainers`

A double-entry payment ledger built to answer one question: what does it take to *prove* money is never created or destroyed?

- **8 ledger invariants enforced in the database** — constraints, triggers and role grants, not application code
- **Idempotent transfers + transactional outbox to Kafka**, with ordered locking: 0 deadlocks across 41,281 contended transfers (87 of 100 died when the lock order was broken on purpose)
- **Measured, not assumed:** SERIALIZABLE + retries was ~10% faster on uncontended traffic but refused 59% of requests on a hot account — so the default stayed, and the trade-off is documented across 9 ADRs
- **92 integration tests** against real PostgreSQL and Kafka, jqwik property tests, and one OpenTelemetry trace from HTTP request to Kafka consumer

<a href="https://github.com/Baran-Ozkann/ledger-payment-core/blob/main/load/RESULTS.md"><img src="https://github.com/Baran-Ozkann/ledger-payment-core/raw/main/load/charts/tps-by-step.svg" alt="Committed transfers per second under load — uniform vs. hot-account workload" width="720"></a>

<sub>Committed transfers/s as load ramps up: one shared row cuts throughput by a factor of 5.5. <a href="https://github.com/Baran-Ozkann/ledger-payment-core/blob/main/load/RESULTS.md">Full load report →</a></sub>

### [settlement-reconciliation](https://github.com/Baran-Ozkann/settlement-reconciliation) · *in progress*
`Java 21` `Spring Boot` `PostgreSQL` `Kafka`

Reconciles ledger events against bank/PSP settlement files: idempotent file ingestion, rule-based matching, and a break lifecycle with a full audit trail. Built on top of ledger-payment-core.

### [hybrid-quantum-portfolio](https://github.com/Baran-Ozkann/hybrid-quantum-portfolio)
`Python` `Q#` `PyTorch`

Hybrid quantum–classical portfolio optimization, built during the Microsoft AI Innovators internship (2026). A 30-seed stability study and an out-of-sample backtest showed the in-sample Sharpe edge was indistinguishable from chance — and the write-up says so.

### [contactsheet-yt](https://github.com/Baran-Ozkann/contactsheet-yt)
`TypeScript` `Chrome / Edge extension`

Hides videos from playlists you choose on the YouTube homepage. Local-only — no server, no telemetry.

### [bist-mtf-signal-indicator](https://github.com/Baran-Ozkann/bist-mtf-signal-indicator)
`Pine Script v6`

A 13-layer, 4-timeframe signal indicator for Borsa İstanbul. Calibration showed 11 of the 13 layers added no measurable signal and the system underperformed buy-and-hold; the findings are documented rather than tuned away.

---

## Toolbox

**Backend** — Java 21, Spring Boot, PostgreSQL, Kafka, Flyway
**Testing & observability** — JUnit, Testcontainers, jqwik, k6, Prometheus, Grafana, Tempo, OpenTelemetry
**Infra** — Docker Compose, GitHub Actions
**Also** — Python, PyTorch, Q#, TypeScript

## Now

- Finishing **settlement-reconciliation**
- Looking for **Summer 2027 software engineering internships**
