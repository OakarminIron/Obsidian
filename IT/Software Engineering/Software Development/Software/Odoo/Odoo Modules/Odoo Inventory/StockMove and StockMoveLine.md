SELECT 
	sml_count.move_line_count,	
	sm.company_id,
	sm.id,
	sm.picking_id	   
FROM 
	stock_move sm
JOIN (SELECT move_id, COUNT(*) as move_line_count
      FROM stock_move_line
      GROUP BY move_id
      HAVING  COUNT(*) >= 3) sml_count ON sml_count.move_id = sm.id
WHERE 
	   sm.picking_id is not null 
ORDER BY 1 DESC LIMIT 30