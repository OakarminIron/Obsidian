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
