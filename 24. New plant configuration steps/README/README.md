## New plant configuration steps


1. Creation of Plant
SPRO → IMG → Enterprise Structure → Definition → Logistics-general → Define, Copy, delete, check plant
→ Define Plant

2. Creation of Storage Location (C)
SPRO → IMG → Enterprise Structure → Definition → Material Management → Maintain Storage Location

3. Assign Plant to Company Code (C)
SPRO → IMG → Enterprise Structure → Assignment → Logistics-general → Assign Plant to Company Code

4. Assign Pur.org. to Plant (C)
SPRO → IMG → Enterprise Structure → Assignment → Material Management → Assign Pur. Org. to Plant

5. Assign Sales Org. Distribution Channel to Plant (C)
SPRO → IMG → Enterprise Structure → Assignment → Sales & Distribution → Assign Sales Org. Distribution Channel to Plant

6. Define Shipping Point to Plant
SPRO → IMG → Enterprise Structure → Definition → Logistics Execution → Assign Shipping Point to Plant

7. Assign Shipping Point to Plant
SPRO → IMG → Enterprise Structure → Assignment → Logistics Execution → Assign Shipping Point to Plant

8. Define Business Place
SPRO → SAP IMG settings → Cross Application components → General Application functions →
Business place / Place of Business → Define Business place → Enter company code → Enter the Business Place

9. Assign Business Place to Plants
SPRO → SAP IMG settings → Cross Application components → General Application functions →
Business place / Place of Business → Assign Business Place to Plants
Assign Plant for your Business Place

10. Assign Shipping Points or OVL2 Transaction
SPRO → IMG → Logistics Execution → Shipping → Basic Shipping Functions →
Shipping Points and Goods Receiving Point Determination → Assign Shipping Points

Assign Shipping Condition, Plant, shipping Point

11. Define Attributes of Material Types or OMS2 Transaction (C) ***Mandatory for stock posting***
SPRO → IMG → Logistics General → Material Master → Basic Settings → Material Types → Define Attributes of Material Types

Select Material Type and click on QTY/Value Updating

Here select qty. update & value update for your Plant(valuation area)

12. Plant Parameters under Inventory Management (C) ***Mandatory for stock posting***
SPRO → IMG → Material Management → Inventory Management and Physical Inventory → Plant Parameters

Enter the Plant and click on Save

13. Material Ledger Active (OMX3) (C)  

Assign material ledger types to valuation Area

SPRO → IMG → Controlling → General Controlling → Multiple Valuation Approaches / Transfer Prices
→ Basic Settings → Check Material Ledger Settings → Assign material ledger types to valuation Area

Assign Material Ledger Type to Valuation Area

14. Activate Material Ledger (OMX1 Transaction) (C)
SPRO → IMG → Controlling → General Controlling → Multiple Valuation Approaches / Transfer Prices
→ Basic Settings → Check Material Ledger Settings → Activate Valuation Areas for Material Ledger
→ Activate Material Ledger

Activation Valuation Areas for Material Ledger

15. Group Together Valuation Areas or OBYC Transaction (C)
SPRO → IMG → Material Management → Valuation and Account Assignment → Account Determination
→ Account Determination without Wizard → Group together Valuation Areas

Assign Valuation Grouping code to your Plant

16. Define Shipping Data for Plants
SPRO → IMG → Material Management → Purchasing → Purchase Order
→ Set up STO → Define Shipping Data for Plants

Assign Sales area and Customer for your respective Plant