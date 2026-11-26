# Annotation Correction Log

## 1. Purpose
This document records annotation corrections identified during quality control (QC) reviews on a customer-service intent classification dataset. It aims to:
- Document annotation errors and their root causes
- Record updated labels and error categories
- Identify recurring error patterns and edge cases
- Support guideline refinements and dataset verification

## 2. Correction Summary

| ID | Original Label | Corrected Label | Error Category |
| :--- | :--- | :--- | :--- |
| 026 | `order_tracking` | `delivery_issue` | Tracking vs. Delivery Issue |
| 049 | `product_complaint` | `refund_request` | Product Complaint vs. Refund |
| 065 | `product_complaint` | `refund_request` | Product Complaint vs. Refund |
| 066 | `refund_request` | `cancellation` | Cancellation vs. Refund |
| 082 | `order_tracking` | `delivery_issue` | Tracking vs. Delivery Issue |
| 089 | `product_complaint` | `cancellation` | Product Complaint vs. Cancellation |
| 105 | `delivery_issue` | `refund_request` | Delivery Issue vs. Refund |

## 3. Detailed Corrections

### Correction 026 — Tracking vs. Delivery Issue
- **Customer Message:** "My package is late. Can you tell me where it is?"
- **Original Label:** `order_tracking`
- **Corrected Label:** `delivery_issue`
- **Reason:** Although the user asks for the package location, the core issue reported is a late delivery.
- **Action:** Update label from `order_tracking` to `delivery_issue`.

### Correction 049 — Product Complaint vs. Refund
- **Customer Message:** "The product is damaged. Can you send me a replacement or give me a refund?"
- **Original Label:** `product_complaint`
- **Corrected Label:** `refund_request`
- **Reason:** Damage is mentioned as context, while a refund is explicitly requested as a resolution option.
- **Action:** Update label from `product_complaint` to `refund_request`.

### Correction 065 — Product Complaint vs. Refund
- **Customer Message:** "The item arrived broken. I want my money back."
- **Original Label:** `product_complaint`
- **Corrected Label:** `refund_request`
- **Reason:** The customer states an explicit desired resolution (`refund_request`) rather than only reporting a defect.
- **Action:** Update label from `product_complaint` to `refund_request`.

### Correction 066 — Cancellation vs. Refund
- **Customer Message:** "Can I cancel my order and get a refund?"
- **Original Label:** `refund_request`
- **Corrected Label:** `cancellation`
- **Reason:** Canceling the order is the primary action requested, with the refund tied to that cancellation.
- **Action:** Update label from `refund_request` to `cancellation`.

### Correction 082 — Tracking vs. Delivery Issue
- **Customer Message:** "My package was marked as delivered, but it's nowhere to be found."
- **Original Label:** `order_tracking`
- **Corrected Label:** `delivery_issue`
- **Reason:** A missing package after a "delivered" status is a delivery problem, not a standard tracking lookup.
- **Action:** Update label from `order_tracking` to `delivery_issue`.

### Correction 089 — Product Complaint vs. Cancellation
- **Customer Message:** "The item is damaged. Can I cancel the order and get a refund?"
- **Original Label:** `product_complaint`
- **Corrected Label:** `cancellation`
- **Reason:** The primary requested action is order cancellation despite the damaged item context.
- **Action:** Update label from `product_complaint` to `cancellation`.

### Correction 105 — Delivery Issue vs. Refund
- **Customer Message:** "I want a refund because my package never arrived."
- **Original Label:** `delivery_issue`
- **Corrected Label:** `refund_request`
- **Reason:** The undelivered package explains why the customer is asking, while `refund_request` is the explicit resolution sought.
- **Action:** Update label from `delivery_issue` to `refund_request`.

## 4. Error Pattern Analysis
- **Tracking vs. Delivery Issue (IDs 026, 082):** Annotators matched keywords like location or "delivered" instead of capturing delays or missing parcels.
- **Product Complaint vs. Refund Request (IDs 049, 065):** Annotators labeled based on item damage rather than the customer's requested refund outcome.
- **Cancellation vs. Refund Request (ID 066):** Annotators focused on the refund mention instead of the primary order cancellation request.
- **Product Complaint vs. Cancellation (ID 089):** Annotators treated product damage as primary intent instead of order cancellation.
- **Delivery Issue vs. Refund Request (ID 105):** Annotators noted the shipping problem rather than the explicit request for a refund.

## 5. Guideline Updates
- Read the full message and identify the customer's primary intent before relying on single keywords.
- Prioritize explicit requested resolutions (`cancellation` or `refund_request`) over background problem descriptions when defined by project rules.
- Separate neutral tracking inquiries (`order_tracking`) from late or missing delivery reports (`delivery_issue`).

## 6. Follow-Up Actions & Correction Status
- Apply label updates to the working dataset and re-run QA checks on modified records.
- Add these edge cases to the annotator training guide and monitor future batches for recurrence.

| Status | Count |
| :--- | :---: |
| Corrections Identified | 7 |
| Corrections Pending Dataset Update | 7 |
| Corrections Verified | 0 |
