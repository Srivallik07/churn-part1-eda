# Data Quality Report

## Executive Summary
Audited 7 datasets. Key issues found that require treatment before modeling.

---

## customers.csv
| Issue | Details | Recommendation |
|-------|---------|---------------|
| Missing values | `age`: 0% null, `gender`: 4.75% null | Impute or flag as unknown |
| Duplicate customer_ids | 0 rows | Keep first occurrence |

## orders.csv
| Issue | Details | Recommendation |
|-------|---------|---------------|
| Negative order_value | 511 rows (likely refunds) | Keep but flag with `is_refund=1` |
| Date range | 2023-01-01 to 2023-12-31 | Consistent, no future dates |
| Outliers in order_value | P99 = ₹2500 | Cap or log-transform for modeling |

## support_tickets.csv
| Issue | Details | Recommendation |
|-------|---------|---------------|
| Missing resolution_date | 20% null (open tickets) | Treat as still open |

## churn_labels.csv
| Issue | Details | Recommendation |
|-------|---------|---------------|
| Class imbalance | 19.6% churned | Use class weights or SMOTE in modeling |

## Join Key Integrity
- 0 customer_ids in orders have no record in customers.csv → investigate
- All churn labels map to valid customer records ✓

## Leakage Warning (Critical for Part 3)
The following columns must NOT be used as model features:
- `days_to_churn` — direct leakage of the target
- Any activity after the customer snapshot date
- `churn_date` if present
