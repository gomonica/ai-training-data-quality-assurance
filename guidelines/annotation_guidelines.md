# Customer Support Intent Annotation Guidelines

## 1. Purpose
This guideline defines how to classify customer support messages into predefined intent categories so annotators assign consistent labels across similar messages.

## 2. Intent Categories
The dataset uses six intent categories:
- `order_tracking`
- `delivery_issue`
- `refund_request`
- `cancellation`
- `product_complaint`
- `general_question`

## 3. Label Definitions

### 3.1 `order_tracking`
Use when the customer asks for the current status, shipping progress, or location of an order without reporting a delivery failure or delay problem.
- Examples:
  - "Where is my order?"
  - "Can you tell me where my package is?"
  - "What is the status of my shipment?"

### 3.2 `delivery_issue`
Use when the customer reports a delivery problem such as a late arrival, missing/lost package, or failed delivery—and is not primarily asking for a refund or cancellation.
- Examples:
  - "My package is late."
  - "My order was supposed to arrive yesterday."
  - "My package hasn't arrived yet."

### 3.3 `refund_request`
Use when the customer explicitly asks for a refund or their money back as the primary desired resolution (unless order cancellation is the primary action requested).
- Examples:
  - "I want a refund."
  - "Can I get my money back?"
  - "I'd like to request a refund."

### 3.4 `cancellation`
Use when the customer explicitly asks to cancel or stop an order.
- Examples:
  - "I want to cancel my order."
  - "Please cancel my purchase."
  - "Can you cancel order #12345?"

### 3.5 `product_complaint`
Use when the customer reports a defect, damage, wrong item/size, or quality issue with the product itself and does not explicitly request a refund or cancellation.
- Examples:
  - "The product arrived damaged."
  - "The item is broken."
  - "The product doesn't work."

### 3.6 `general_question`
Use for general inquiries about policies, shipping coverage, hours, or payment methods that do not fit the other five categories.
- Examples:
  - "Do you deliver on weekends?"
  - "What payment methods do you accept?"
  - "What are your business hours?"

## 4. General Annotation Rules & Priority
1. **Read the full message first:** Identify the customer's main goal rather than reacting to a single keyword.
2. **Apply resolution priority on multi-intent messages:**
   - If the customer explicitly asks to **cancel** an order (even if mentioning damage or a refund), assign `cancellation`.
   - If the customer explicitly asks for a **refund** as the desired resolution (even if mentioning damage or late delivery), assign `refund_request`.
   - If there is no explicit refund or cancellation request, assign `delivery_issue` for late/missing/failed delivery, `product_complaint` for item defects/damage/mismatch, or `order_tracking` for status/location checks.
3. **Avoid assumptions:** Do not infer facts or intents that are not stated in the message.

## 5. Ambiguous & Edge Cases
- **Message:** "My package is late. Can I get a refund?"
  - **Label:** `refund_request` (explicit refund request takes precedence over the delivery delay context).
- **Message:** "The item arrived damaged. Can I cancel the order and get my money back?"
  - **Label:** `cancellation` (primary action requested is canceling the order).
- **Message:** "The item arrived damaged, and I want a refund."
  - **Label:** `refund_request` (explicit refund request takes precedence over product damage alone).

## 6. Difficulty Levels (`easy`, `medium`, `hard`)
- `easy`: Single, clear intent with straightforward wording.
- `medium`: Contextual details, timing/condition nuances, or slightly indirect phrasing with one clear intent.
- `hard`: Overlapping intents or edge cases requiring priority rules (such as combining product damage/delay with a refund or cancellation request).

## 7. Quality Check & Review
During quality control, review annotations for:
- Incorrect or inconsistent labels across similar messages
- Keyword-only labeling that misses the primary intent
- Confusion between `order_tracking` vs. `delivery_issue`, `delivery_issue` vs. `refund_request`, `product_complaint` vs. `refund_request`, and `cancellation` vs. `refund_request`
- Unclear cases that should be flagged for review rather than guessed
