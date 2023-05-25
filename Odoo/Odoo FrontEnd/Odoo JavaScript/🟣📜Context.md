An important concept in the Odoo JavaScript is the context: it provides a way for code to give more context to a function call or a rpc, so other parts of the system can properly react to that information. In some way, it is like a bag of information that is propagated everywhere. It is useful in some situations, such as letting the Odoo server know that a model rpc comes from a specific form view, or activating/disabling some features in a component.

There are two different contexts in the Odoo web client: 
	- the [[🟣📜User Context]] and 
	- the [[🟣📜Action Context]]

(so, we should be careful when using the word context: it could mean a different thing depending on the situation).