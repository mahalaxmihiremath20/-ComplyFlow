# Sample Discrepancy Scenario

## Scenario: Potential Duplicate Invoice

### Input Records

A fictional business has two records:

| Field | Record A | Record B |
|---|---|---|
| Supplier | ABC Traders | ABC Traders |
| Invoice Number | INV-1042 | INV-1042 |
| Invoice Date | 12 Nov 2026 | 12 Nov 2026 |
| Amount | ₹8,450 | ₹8,450 |

### What the System Detects

The two records share the same supplier, invoice number, date, and amount.

### Radar Finding

**Potential duplicate record**

The system flags both entries for manual verification.

### Suggested Action

Review both records against the original invoice and confirm whether the same invoice was entered twice.

### Why This Matters

Duplicate records may lead to inaccurate bookkeeping and should be resolved before further compliance preparation.

### Important Note

This is a fictional example showing the proposed behavior. It is not a live detection result from implemented software.
