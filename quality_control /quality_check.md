# Annotation Quality Check Report

## 1. Purpose
This report documents a quality check review of a sample from `data/annotated_dataset.csv` against `guidelines/annotation_guidelines.md` to verify label accuracy, consistency, and handling of multi-intent or edge cases.

## 2. Quality Check Method
A sample of 10 records spanning `easy`, `medium`, and `hard` difficulty levels was reviewed. For each record, the reviewer checked:
- Original label vs. expected/correct label under the guidelines
- Verification status (`Correct` / `Incorrect`)
- Concise rationale for the decision

## 3. Quality Check Results (Standard & Medium Cases)

### Case 1 — ID `001` (`easy`)
- **Customer Message:** "Where is my order?"
- **Original Label:** `order_tracking`
- **Correct Label:** `order_tracking`
- **Result:** `Correct`
- **Reason:** The customer is asking for the current location or status of the order.

### Case 2 — ID `012` (`medium`)
- **Customer Message:** "I haven't received my order yet. It was supposed to arrive two days ago."
- **Original Label:** `delivery_issue`
- **Correct Label:** `delivery_issue`
- **Result:** `Correct`
- **Reason:** The customer reports that the expected delivery date has passed.

### Case 3 — ID `023` (`medium`)
- **Customer Message:** "I want my money back because the item isn't what I expected."
- **Original Label:** `refund_request`
- **Correct Label:** `refund_request`
- **Result:** `Correct`
- **Reason:** The customer explicitly requests a refund.

## 4. Edge Case Review (`hard` / Multi-Intent Cases)

### Case 4 — ID `026`
- **Customer Message:** "My package is late. Can you tell me where it is?"
- **Original Label:** `delivery_issue`
- **Correct Label:** `delivery_issue`
- **Result:** `Correct`
- **Reason:** Although the customer asks about location, they report a late delivery, making the delivery issue the primary intent.

### Case 5 — ID `049`
- **Customer Message:** "The product is damaged. Can you send me a replacement or give me a refund?"
- **Original Label:** `refund_request`
- **Correct Label:** `refund_request`
- **Result:** `Correct`
- **Reason:** The customer explicitly includes a refund as a requested resolution.

### Case 6 — ID `065`
- **Customer Message:** "The item arrived broken. I want my money back."
- **Original Label:** `refund_request`
- **Correct Label:** `refund_request`
- **Result:** `Correct`
- **Reason:** The customer reports product damage but explicitly requests a refund.

### Case 7 — ID `066`
- **Customer Message:** "Can I cancel my order and get a refund?"
- **Original Label:** `cancellation`
- **Correct Label:** `cancellation`
- **Reason:** Canceling the order is the primary request, with the refund tied to the cancellation.

### Case 8 — ID `082`
- **Customer Message:** "My package was marked as delivered, but it's nowhere to be found."
- **Original Label:** `delivery_issue`
- **Correct Label:** `delivery_issue`
- **Reason:** The customer reports a missing package despite a "delivered" status.

### Case 9 — ID `089`
- **Customer Message:** "The item is damaged. Can I cancel the order and get my money back?"
- **Original Label:** `cancellation`
- **Correct Label:** `cancellation`
- **Reason:** The customer explicitly requests order cancellation, with a refund associated with the cancellation outcome.

### Case 10 — ID `105`
- **Customer Message:** "I want a refund because my package never arrived."
- **Original Label:** `refund_request`
- **Correct Label:** `refund_request`
- **Reason:** The customer reports a delivery problem but explicitly requests a refund as the desired resolution.

## 5. Quality Observations
The most challenging messages involve overlapping intents or explicit resolutions alongside a problem statement—specifically:
- `order_tracking` vs. `delivery_issue`
- `delivery_issue` vs. `refund_request`
- `product_complaint` vs. `refund_request`
- `cancellation` vs. `refund_request`

Clear priority rules and full-message reading help resolve these cases consistently.

## 6. Quality Improvement Recommendations
- Always read the full message before assigning a label rather than relying on single keywords.
- Distinguish neutral tracking queries from late or missing delivery reports.
- Apply explicit priority rules consistently when cancellation or refund requests appear alongside delivery or product issues.
- See [correction_log.md](./correction_log.md) for historical error tracking and dataset updates.

## 7. Summary
All 10 reviewed sample records (including 7 `hard` edge cases) align with the annotation guidelines. Consistent rule application on multi-intent messages remains the primary focus for ongoing quality control.
