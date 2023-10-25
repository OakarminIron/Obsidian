
Isolation ensures that all transactions run in an isolated environment. 
That enables running transactions concurrently because transactions don’t interfere with each other.
This ensures that the results of one transaction do not affect the results of another transaction.

Isolation Level
	- Read uncommitted
	- Read committed , see committed staff
		- Repeatable read, see committed update at the beginning of transaction
	- Serializable  , it's easy but cost expensively slow
	- versioning can get rid of repeatable read
	- ![[IsolationLevel.png]]

Read pheomena
	- Dirty Reads ,,, commit မပြီးသေးတဲ့ transaction ကို သွားဖတ်မိတာမျိုး အဲ့tran က rollback သွားတာမျိုး
	- Non-repeatable reads, commit ပြီးတဲ့ record ကိုဖတ်ရင်းမတူတဲ့ value ဖြစ်လာတာမျိုး  


![[non_repeatable_read.png]]
	- Phanton Reads ,, Range quaries
![[phantom_read.png]]
	- (Lost updates) , 