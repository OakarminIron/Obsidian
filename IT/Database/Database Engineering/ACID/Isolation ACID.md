Isolation ensures that all transactions run in an isolated environment. That enables running transactions concurrently because transactions don’t interfere with each other.

Isolation Level
	- Read uncomitted
	- Read commited , see committed staff
		- Repeatable read, see committed update at the begining of transaction
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