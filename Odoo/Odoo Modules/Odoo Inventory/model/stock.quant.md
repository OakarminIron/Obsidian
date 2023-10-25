`Quant` indicates a _specific stock quantity_ of the _same product_ that entered your warehouse at a specific moment in time in one specific operation; in a _single lot_ (batch) if lot tracking is enabled. 

Let's give an example. You purchased 10 pieces a week ago, you received 6 pieces yesterday and today the remaining 4 pieces arrive. In this case, two `quants` will be created: 1 with 6 pieces, another one with 4 pieces. Should the batch with 4 pieces be linked to individual Lot (serial) numbers, the result will be 4 separate `quants`.

The `Quant`` table stores the current state of stock (per location). It is updated each time a stock move is set to **done** and has 3 main impacts:

-   A `quant` optimizes the computation (e.g. quantity available), because a `quant` only contains information about the current stock (not the past or the future). The volume is smaller and doesn’t grow in time
-   A `quant`  will be used in `FIFO`, `LIFO` and `FEFO` costing, as we need to match the incoming and outgoing moves for a correct stock valuation
-   A `quant` can also be used for upstream/downstream traceability and lot management; a `quant` contains the information about lots. `Quant` history displays a list of stock moves indicating the current stock level.

In case a `quant` has been reserved,  you can see the related stock move in the **Reserved for Move** field. `Quants` can be split in order to reserve only the quantities needed.