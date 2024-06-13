``` bash
source /home/odoo/Documents/Projects/Odoo/venv16/bin/activate
pip install wheel
pip freeze > /home/odoo/Documents/Projects/Odoo/venv16/requirements.txt
pip wheel --wheel-dir=/home/odoo/Documents/Projects/Odoo/venv16wheel -r /home/odoo/Documents/Projects/Odoo/venv16/requirements.txt
deactivate
```


```
source /new/location/bin/activate
pip install --no-index --find-links=/new/location/ -r /new/location/requirements.txt
```


Navigate to the Odoo project directory:` cd /home/odoo/Documents/Projects/Odoo/v16`
Activate the virtual environment:`source ./bin/activate`
Generate requirements :` pip freeze > requirements.txt`
Move directory for the packages: `cd ../`
Create a directory for the packages: `mkdir v16-packages`
Download the packages: `pip download -r /home/odoo/Documents/Projects/Odoo/v16/requirements.txt -d /home/odoo/Documents/Projects/Odoo/v16-packages`


Create a virtual environment : `python3 -m venv o16new`
Copy the requirement text file
Install :` pip install --no-index --find-links=/path/to/v16-packages -r /path/to/requirements.txt`
