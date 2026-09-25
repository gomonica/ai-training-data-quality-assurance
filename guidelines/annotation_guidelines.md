## Customer Support Intent Annotation Guidelines
### 1. Purpose

This guideline defines how to classify customer support messages into predefined intent categories.

The goal is to ensure that different annotators assign consistent labels to similar customer messages.

### 2. Intent Categories

The dataset contains six intent categories:

- order_tracking

- delivery_issue

- refund_request

- cancellation

- product_complaint

- general_question

### 3. Label Definitions
### 3.1 order_tracking

Use order_tracking when the customer wants to know the status, location, or current progress of an order.

Examples:

"Where is my order?"

"Can you tell me where my package is?"

"What is the status of my shipment?"

Do not use this label when the customer is reporting that the delivery is late or has failed.

### 3.2 delivery_issue

Use delivery_issue when the customer reports a problem with the delivery, such as a late, missing, or failed delivery.

Examples:

"My package is late."

"My order was supposed to arrive yesterday."

"My package hasn't arrived yet."

### 3.3 refund_request

Use refund_request when the customer explicitly asks for their money back or requests a refund.

Examples:

"I want a refund."

"Can I get my money back?"

"I'd like to request a refund."

### 3.4 cancellation

Use cancellation when the customer wants to cancel an order.

Examples:

"I want to cancel my order."

"Please cancel my purchase."

"Can you cancel order #12345?"

### 3.5 product_complaint

Use product_complaint when the customer reports a problem with the product itself, such as damage, defects, or poor product quality.

Examples:

"The product arrived damaged."

"The item is broken."

"The product doesn't work."

### 3.6 general_question

Use general_question when the customer asks a general question that does not fit the other five categories.

Examples:

"Do you deliver on weekends?"

"What payment methods do you accept?"

"What are your business hours?"

### 4. General Annotation Rules
### Rule 1: Focus on the customer's main intent

Choose the label that best represents what the customer is primarily trying to achieve.

### Rule 2: Look for explicit requests

If the customer explicitly asks for a refund, use refund_request.

If the customer explicitly asks to cancel an order, use cancellation.

### Rule 3: Distinguish tracking from delivery problems

Use order_tracking when the customer is simply asking about the status or location of an order.

Use delivery_issue when the customer reports that the delivery is late, missing, or unsuccessful.

### Rule 4: Product problems take priority when the issue is about the product

If the customer reports that the product is damaged, broken, or defective, use product_complaint.

### 5. Ambiguous Cases

Some messages may contain more than one possible intent.

Example:

** "My package is late. Can I get a refund?" **

Possible labels:

delivery_issue

refund_request

For this project, use the customer's explicit request as the primary intent.

Therefore:

refund_request

Another example:

"The item arrived damaged and I want my money back."

The customer explicitly requests a refund.

Therefore:

refund_request

### 6. Annotation Quality Principles

Annotators should:

- Read the entire customer message before assigning a label.

- Follow the definitions in this guideline.

- Avoid making assumptions about information that is not stated.

- Use the most specific applicable label.

- Flag unclear cases for review instead of guessing when the intent cannot be determined confidently.

### 7. Quality Check

During quality control, annotations should be reviewed for:

- Incorrect labels

- Inconsistent labeling

- Misinterpretation of customer intent

- Confusion between similar categories

- Failure to follow the annotation rules

Examples of commonly confused categories include:

- order_tracking vs delivery_issue

- delivery_issue vs refund_request

- product_complaint vs refund_request
