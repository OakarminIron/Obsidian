`Command and Query Responsibility Segregation` separates reads and writes into different models, using commands to update data, and queries to read data.

- Commands should be task-based, rather than `data centric`. ("Book hotel room", not "set Reservation Status to Reserved"). Event နဲ့ဖမ်းမှာ ဖတ်တဲ့ဘက်က IO တွေလဲသက်သာ
- Commands may be placed on a queue for asynchronous processing, rather than being processed synchronously.
- Queries never modify the database. A query returns a DTO that does not encapsulate any domain knowledge.