Check active user counts
```python
# pip install psycopg2-binary
# python x_check_users.py
import psycopg2
from psycopg2 import sql
# Define connection parameters for each cluster
clusters = [
{"host": "localhost", "port": 5432, "user": "odoo", "password": "xxxxx", "database": "15"},
{"host": "localhost", "port": 5433, "user": "odoo", "password": "xxxxx", "database": "16e_a"},
{"host": "localhost", "port": 5433, "user": "odoo", "password": "xxxxx", "database": "16e_b"},
{"host": "localhost", "port": 5434, "user": "odoo", "password": "xxxxx", "database": "17"},
{"host": "localhost", "port": 5435, "user": "odoo", "password": "xxxxx", "database": "17e"},
# Add more clusters as needed
]

# Iterate over clusters and update ir_cron table
for cluster in clusters:
	try:
		# Establish a connection
		connection = psycopg2.connect(**cluster)
		cursor = connection.cursor()
		# Check active user count in res_users table
		count_users_query = sql.SQL("SELECT COUNT(*) FROM res_users WHERE active = true;")
		cursor.execute(count_users_query)
		active_users_count = cursor.fetchone()[0]
		print(f"{cluster['database']} on port {cluster['port']} - Active users count: {active_users_count}")
	except Exception as e:
		print(f"Error connecting to {cluster['database']} on port {cluster['port']}: {e}")
	finally:
	# Close the cursor and connection
		cursor.close()
		connection.close()
```


set `ir_cron` and admin
```python
for cluster in clusters:
	try:
		# Establish a connection
		connection = psycopg2.connect(**cluster)
		cursor = connection.cursor()
		# Update ir_cron table
		update_cron_query = sql.SQL("UPDATE ir_cron SET active = False;")	
		cursor.execute(update_cron_query)	
		# Update res_users table	
		update_res_users_query = sql.SQL("UPDATE res_users SET login='odoo', password=1, active=true WHERE id=1;")	
		cursor.execute(update_res_users_query)	
		# Commit the changes	
		connection.commit()	
		print(f"Update successful for {cluster['database']} on port {cluster['port']}")	
	except Exception as e:	
		print(f"Error updating {cluster['database']} on port {cluster['port']}: {e}")	
	finally:	
		# Close the cursor and connection	
		cursor.close()	
		connection.close()
```