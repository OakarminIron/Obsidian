A method for solving optimization problems by breaking them down into smaller sub-problems and using a bounding function.

The "branch" step involves dividing the problem into smaller sub-problems or branches. You start with the original problem and create one or more sub-problems by decomposing it into simpler, usually smaller, instances. These sub-problems are typically formed by making choices or decisions regarding the variables or parameters of the problem. Each sub-problem represents a different potential solution or path in the search space.

The "bound" step involves estimating the minimum or maximum value that can be obtained from a sub-problem without solving it completely. These bounds are used to guide the search and eliminate sub-problems that cannot lead to better solutions than the ones already found. Bounds help in pruning the search tree, reducing the number of sub-problems that need to be explored.


အကုန်လုံးအသေးစိတ်လိုက်တွက်မနေဘူး ပထမ branch ခွဲတယ် / ပဏာမ bound ဖြတ်လိုက်တယ်