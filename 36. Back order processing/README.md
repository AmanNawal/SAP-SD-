## Backorder processing

Backorder Processing (BOP) in **SAP SD (Sales and Distribution)** refers to the functionality that manages **sales orders which could not be fully confirmed due to insufficient availability of stock** at the time of order entry.

It ensures that **limited available inventory is redistributed in a controlled and prioritized way** when stock becomes available.

---

**Transaction Codes:**

* V_RA – Backorder Processing (collective)
* V_V2 – Sales order processing (individual)

### 1. What Is a Backorder in SAP SD?

A **backorder** occurs when:

* A sales order is created
* The requested quantity **cannot be fully confirmed**
* Result: **Confirmed quantity < Order quantity**

This typically happens due to:

* Insufficient stock
* Future stock availability
* Higher-priority orders consuming inventory

---

### 2. Purpose of Backorder Processing

Backorder Processing allows you to:

* Reconfirm or redistribute available stock
* Prioritize important customers or documents
* Reduce delivery delays
* Improve customer service and fulfillment reliability

---


### 3. Common Business Example

* Customer A (key account) and Customer B place orders
* Stock is limited
* Customer B’s order is confirmed first
* Later, BOP is executed
* Stock is reallocated to Customer A based on priority

---

