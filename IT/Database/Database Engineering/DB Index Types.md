[[Bitmap index]]
	
[[Dense Index]]

[[Sprase Index]]
A sparse index in databases is a file with pairs of keys and pointers for every [block](https://en.wikipedia.org/wiki/Block_(data_storage) "Block (data storage)") in the data file. Every key in this file is associated with a particular pointer _to the block_ in the sorted data file. In clustered indices with duplicate keys, the sparse index points _to the lowest search key_ in each block.
m
[[Reverse Index]]
A reverse-key index reverses the key value before entering it in the index. E.g., the value 24538 becomes 83542 in the index. Reversing the key value is particularly useful for indexing data such as sequence numbers, where new key values monotonically increase.


[[Primary Index]]
[[Secondary Index]]

[[Hash Index]]