## JDBC Architecture

- Let us consider a simple example for understanding.
- Imagine you want to order food at a restaurant.
- Then the following is the hierarchy:
    - Waiter : JDBC API
    - Restaurant manager : JDBC Driver manager
    - Food order : SQL Query
    - Prepared food : Result
    - Kitchen : database
    - You(customer) : Java application
    - chef : Database driver
- Now look at the following architecture diagram : 

```
  ┌─────────────────────────────────────────┐
  │         Java Application Layer          │
  └────────────────────┬────────────────────┘
                       │ (Uses standard API interfaces)
  ┌────────────────────▼────────────────────┐
  │              JDBC API Layer             │
  │     (Connection, Statement, etc.)       │
  └────────────────────┬────────────────────┘
                       │ (Manages drivers)
  ┌────────────────────▼────────────────────┐
  │           JDBC Driver Manager           │
  └────────────────────┬────────────────────┘
                       │ (Translates calls)
  ┌────────────────────▼────────────────────┐
  │            JDBC Driver Layer            │
  │  (MySQL Driver, Oracle Driver, etc.)    │
  └────────────────────┬────────────────────┘
                       │ (Database specific protocol)
  ┌────────────────────▼────────────────────┐
  │             Database Layer              │
  └─────────────────────────────────────────┘
```


