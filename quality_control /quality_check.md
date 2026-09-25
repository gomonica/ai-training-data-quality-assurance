Annotation Quality Check
1. Purpose

This quality check reviews a sample of annotated customer support data to identify incorrect labels, inconsistent annotations, and ambiguous cases.

The review is based on the annotation guidelines defined for this project.

2. Quality Check Method

A sample of annotations is reviewed across different difficulty levels:

Easy cases

Medium cases

Hard cases

Each reviewed annotation is checked against the annotation guidelines.

The reviewer records:

Original label

Correct label

Whether the annotation is correct

Reason for the decision

3. Quality Check Results
Case 1

ID: 001

Customer Message:

"Where is my order?"

Original Label: order_tracking

Correct Label: order_tracking

Result: Correct

Reason: The customer is asking for the current location or status of the order.

Case 2

ID: 012

Customer Message:

"I haven't received my order yet. It was supposed to arrive two days ago."

Original Label: delivery_issue

Correct Label: delivery_issue

Result: Correct

Reason: The customer reports that the expected delivery date has passed.

Case 3

ID: 023

Customer Message:

"I want my money back because the item isn't what I expected."

Original Label: refund_request

Correct Label: refund_request

Result: Correct

Reason: The customer explicitly requests a refund.

Case 4

ID: 026

Customer Message:

"My package is late. Can you tell me where it is?"

Original Label: delivery_issue

Correct Label: delivery_issue

Result: Correct

Reason: Although the customer asks about the package location, they explicitly report that the package is late. The delivery problem is the primary intent.

Case 5

ID: 049

Customer Message:

"The product is damaged. Can you send me a replacement or give me a refund?"

Original Label: refund_request

Correct Label: refund_request

Result: Correct

Reason: The customer explicitly includes a refund as a requested resolution.

4. Edge Case Review
Case 6

ID: 065

Customer Message:

"The item arrived broken. I want my money back."

Original Label: refund_request

Correct Label: refund_request

Result: Correct

Reason: The customer reports product damage but explicitly requests a refund.

Case 7

ID: 066

Customer Message:

"Can I cancel my order and get a refund?"

Original Label: cancellation

Correct Label: cancellation

Result: Correct

Reason: The primary request is to cancel the order. The refund is associated with the cancellation.

Case 8

ID: 082

Customer Message:

"My package was marked as delivered, but it's nowhere to be found."

Original Label: delivery_issue

Correct Label: delivery_issue

Result: Correct

Reason: The customer reports a missing package despite the delivery status showing that it was delivered.

Case 9

ID: 089

Customer Message:

"The item is damaged. Can I cancel the order and get my money back?"

Original Label: cancellation

Correct Label: cancellation

Result: Correct

Reason: The customer explicitly asks to cancel the order. The refund is requested as part of the cancellation outcome.

Case 10

ID: 105

Customer Message:

"I want a refund because my package never arrived."

Original Label: refund_request

Correct Label: refund_request

Result: Correct

Reason: The customer reports a delivery problem but explicitly requests a refund as the desired resolution.

5. Quality Observations

The reviewed cases show that the most challenging annotations involve multiple possible intents.

The main sources of ambiguity are:

order_tracking vs delivery_issue

delivery_issue vs refund_request

product_complaint vs refund_request

cancellation vs refund_request

The annotation guideline helps resolve these cases by focusing on the customer's primary intent and explicit requested resolution.

6. Quality Improvement Recommendations

Based on the review, the annotation guideline should continue to emphasize:

Reading the full customer message.

Understanding the customer's primary intent.

Distinguishing a simple tracking question from an actual delivery problem.

Giving priority to explicit refund requests when appropriate.

Distinguishing cancellation requests from refund requests.

Reviewing ambiguous cases carefully instead of relying only on keywords.

7. Summary

The reviewed sample demonstrates that annotation quality depends on consistent application of the labeling rules.

The most important quality-control focus for this dataset is handling messages that contain multiple possible intents.
