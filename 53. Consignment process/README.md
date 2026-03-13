## Consignment process

* Dumping the stocks at customer place and keeping ownership with the company i.e. deliver the goods to customer without rising invoice. When our customer sold the goods to their end customer then we raise invoice to our customer.

We have four steps

* Consignment fill up
* Consignment issue
* Consignment return
* Consignment picks up

---

### Consignment Fill Up

* (CF) Consignment fill up is just dumping the stock at customer place without transferring ownership and without raising invoice.

Order type – **CF / KB**
Item category – **KBN**
Schedule line – **E1**

**(631) movement type** The effect of 631 movement type is:

1. It will reduce the stock from unrestricted stocks and stock will be added to consignment stock.
2. No inventory accounting document generates because CF process is not relevant for invoice.

---

### Consignment Issue

* (CI) when our customer sold the goods to their end customer then our customer inform the same to company.  Then company will do consignment issue process.

Order type – **CF / KE**
Item category – **KEN**
KEN special stock indicator **‘W’** is while doing delivery system considers consignment stock.
Schedule line – **C1**

* **(633) Movement type**

The effect of **633 movement type** is:

1. Stocks will be reduce from consignment stocks.
2. Inventory accounting document will generate and accounting entry is:

**COGS A/c .....Dr**
To,
**Inventory A/c .....Cr**

---

### Consignment returns

* (C0NR) When end customer returns the goods to our customer, then our customer will inform the same to company, then we do consignment returns.

Order type – **CONR / KR**
Item category – **KRN**
KRN special stock indicator **‘W’** is while doing delivery system considers consignment stock.
Schedule line – **D0**

* **(634) movement type**

The effect of **634 movement type** is:

1. The stock will be added to consignment stock.
2. Inventory accounting document will be generate and accounting entry is:

**Inventory A/c .....Dr.**
To, **COGS A/c .....Cr.**

---

### Consignment Pick Up

(CP) If our customer requesting take back materials then we do consignment pick up.

Order type – **CP / KA**
Item category – **KAN**
Schedule line – **F1**

**(632) The effect of 632 movement type is:**

1. Stock will be reduce from consignment stock and add to unrestricted stock.
2. Inventory accounting document will not generate because **CP** is not relevant for invoice.

