# Business Memo: Investigation Priorities Before Retention Campaign

**To:** Product, Marketing, CX Teams  
**From:** Analytics  
**Date:** [today's date]  
**Subject:** What we found in customer data — act before launching campaigns

---

## Summary
We analysed 2,000 customers across orders, support, web activity, and campaigns.
Three findings require immediate attention before any retention spend.

---

## Finding 1: Recency is the single strongest predictor of churn
Customers who have not ordered in the last 60 days churn at 24% vs 15% overall.
The median gap for churned customers is 150 days; for retained customers it is 90 days.
(See Chart 5 in eda_audit.ipynb)

**Recommendation:** Flag all customers with no order in 45+ days for proactive outreach now.

---

## Finding 2: Support tickets are a leading indicator
Customers with 3 or more support tickets churn at 30% — nearly double the baseline.
The top issue type is "delivery delay" (see Chart 4), which suggests an operational
problem that discounts cannot fix.

**Recommendation:** Prioritise resolution of open delivery complaints BEFORE sending
any promotional offer to these customers.

---

## Finding 3: One-time buyers represent the highest-volume churn risk
25% of churned customers made only a single purchase. A discount win-back
is unlikely to work if the first product experience was negative.

**Recommendation:** Investigate product-level satisfaction among single-purchase churners
before designing retention offers for this group.

---

## What the company should NOT do
- Do not give blanket discounts to all customers — it will be wasted on customers
  who were never at risk and may undervalue the brand.
- Do not launch a campaign before fixing the delivery complaint backlog.

---

## Recommended Next Steps (priority order)
1. Resolve open support tickets → then retarget those customers
2. Segment before spending — use RFM (Part 2) to prioritise budget
3. Build a churn model (Part 3) for precise, individual-level scoring
