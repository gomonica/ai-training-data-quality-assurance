Annotation Correction Log
1. Purpose

This document records annotation corrections identified during the quality control review.

The purpose of the correction log is to:

Document identified annotation errors

Explain why the original label was incorrect

Record the corrected label

Identify recurring annotation error patterns

Support future improvements to the annotation guidelines

2. Correction Summary
ID	Original Label	Corrected Label	Error Category
026	order_tracking	delivery_issue	Tracking vs. Delivery Issue
049	product_complaint	refund_request	Product Complaint vs. Refund
065	product_complaint	refund_request	Product Complaint vs. Refund
066	refund_request	cancellation	Cancellation vs. Refund
082	order_tracking	delivery_issue	Tracking vs. Delivery Issue
089	product_complaint	cancellation	Product Complaint vs. Cancellation
105	delivery_issue	refund_request	Delivery Issue vs. Refund
3. Detailed Corrections
Correction 026 — Tracking vs. Delivery Issue

Customer Message:

"My package is late. Can you tell me where it is?"

Original Label: order_tracking

Corrected Label: delivery_issue

Reason:

The customer asks about the package location, but also explicitly states that the package is late.

According to the annotation guidelines, a reported delivery delay should be classified as delivery_issue.

Action:

Change the annotation from order_tracking to delivery_issue.

Correction 049 — Product Complaint vs. Refund

Customer Message:

"The product is damaged. Can you send me a replacement or give me a refund?"

Original Label: product_complaint

Corrected Label: refund_request

Reason:

The customer reports product damage but explicitly includes a refund as one of the requested resolutions.

Action:

Change the annotation from product_complaint to refund_request.

Correction 065 — Product Complaint vs. Refund

Customer Message:

"The item arrived broken. I want my money back."

Original Label: product_complaint

Corrected Label: refund_request

Reason:

Although the product is damaged, the customer's explicit desired resolution is a refund.

Action:

Change the annotation from product_complaint to refund_request.

Correction 066 — Cancellation vs. Refund

Customer Message:

"Can I cancel my order and get a refund?"

Original Label: refund_request

Corrected Label: cancellation

Reason:

The customer's primary request is to cancel the order. The refund is associated with the cancellation request.

Action:

Change the annotation from refund_request to cancellation.

Correction 082 — Tracking vs. Delivery Issue

Customer Message:

"My package was marked as delivered, but it's nowhere to be found."

Original Label: order_tracking

Corrected Label: delivery_issue

Reason:

The customer is reporting a missing package despite the tracking status showing that it was delivered.

This represents a delivery problem rather than a simple request to track an order.

Action:

Change the annotation from order_tracking to delivery_issue.

Correction 089 — Product Complaint vs. Cancellation

Customer Message:

"The item is damaged. Can I cancel the order and get my money back?"

Original Label: product_complaint

Corrected Label: cancellation

Reason:

The customer explicitly asks to cancel the order. The refund is presented as part of the requested cancellation outcome.

Action:

Change the annotation from product_complaint to cancellation.

Correction 105 — Delivery Issue vs. Refund

Customer Message:

"I want a refund because my package never arrived."

Original Label: delivery_issue

Corrected Label: refund_request

Reason:

The customer reports a delivery problem but explicitly requests a refund as the desired resolution.

Action:

Change the annotation from delivery_issue to refund_request.

4. Error Pattern Analysis

The corrections reveal several recurring error patterns.

Pattern 1 — Tracking vs. Delivery Issue

Examples:

ID 026

ID 082

The errors occurred when an annotator focused on tracking-related language without considering the underlying delivery problem.

Pattern 2 — Product Complaint vs. Refund Request

Examples:

ID 049

ID 065

The errors occurred when the product problem was prioritized over the customer's explicit refund request.

Pattern 3 — Cancellation vs. Refund Request

Example:

ID 066

The error occurred because the annotator focused on the refund instead of the primary cancellation request.

Pattern 4 — Product Complaint vs. Cancellation

Example:

ID 089

The error occurred because the product damage was treated as the primary intent even though the customer explicitly requested cancellation.

Pattern 5 — Delivery Issue vs. Refund Request

Example:

ID 105

The delivery problem was identified correctly as part of the situation, but the requested resolution was a refund.

5. Guideline Updates

Based on these corrections, the following principles should be emphasized in the annotation guidelines:

Identify the customer's primary intent.

Read the complete message before assigning a label.

Do not rely solely on keywords.

Distinguish tracking requests from reported delivery problems.

Consider explicit requested resolutions.

Treat cancellation as the primary intent when the customer explicitly asks to cancel an order.

Use refund_request when a refund is explicitly requested as the desired resolution.

6. Follow-Up Actions

The following actions should be performed after the corrections:

Update the affected records in the dataset.

Re-run the quality check on corrected records.

Add the identified edge cases to the annotation guidelines.

Monitor whether similar errors appear in future annotations.

Perform periodic quality checks to maintain annotation consistency.

7. Correction Status
Status	Count
Corrections Identified	7
Corrections Pending Dataset Update	7
Corrections Verified	0

The corrected labels should be updated in the main dataset before the corrections are considered verified.
