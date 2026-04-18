## Add Order (A)

Fields:
- Timestamp: 6 bytes
- Order ID: 8 bytes
- Side: 1 byte
- Shares: 4 bytes
- Price: 4 bytes

offset 0: message type (1)
offset 1: stock locate  (2)
offset 3: tracking number (2)
offset 5: timestamp (6)
offset 11: order id (8)  
offset 19: side (1)  
offset 20: shares (4)  
offset 24: stock (8)  
offset 32: price (4)

## Order Executed (E)

Fields:
- Timestamp: 6 bytes
- Order ID: 8 bytes
- LastShares: 4 bytes
- LastPx: 4 bytes
- ExecutionId: 8 bytes
## Order Deleted (D)

Fields:
- Timestamp: 6 bytes
- Order ID: 8 bytes
- 