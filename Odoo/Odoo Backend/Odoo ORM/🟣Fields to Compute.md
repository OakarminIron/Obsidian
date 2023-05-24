Goals: delay compute
Stored fields are compute first no store fields are low priority

Accessible on environment

{fields:set(ids)}

if record.id in tocompute.get(self, ())


stored fields to compute--> cache 
	if not in cache --> call compute() on prefetch set 
	 then from cache get value

non-store  