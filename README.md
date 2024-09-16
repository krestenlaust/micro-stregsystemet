Micro-Stregsystemet [![Django CI Actions Status](https://github.com/krestenlaust/micro-stregsystemet/workflows/Django%20CI/badge.svg)](https://github.com/krestenlaust/micro-stregsystemet/actions) 
========

Micro-Stregsystemet is a bare-bones stregsystem, where all the fuzz, fun and charm has been cut away. The end goal is to turn the system towards a cashier as opposed customers themselves. This gives more freedom for the system in generel, since there is only authorized users.

The main idea is to discover, how well the core stregsystem serves as a 'real' Point of Sales (PoS) system.


Below is the default readme for the stregsystemet.

Stregsystemet
-------

This is the current stregsystem in the F-Klub.

Branches
-------
 - `master`: The running code on the live system.
 - `next`: The set of changes which will be included in the next release.

Python Environment
-------
For windows using Anaconda and virtual environments:
1. Download and install Anaconda
2. In a shell:
  - `conda create -n stregsystem python=3.11`
  - `activate stregsystem`
  - `pip install -r requirements.txt`
3. ???
4. Profit

For Ubuntu with virtual envs:
1. Install python3 with pip
 - `sudo apt install python3 python3-pip python3-venv`
2. Create virtual environment
 - `python3 -m venv venv`
3. Activate virtualenv
 - `source venv/bin/activate`
4. Install packages
 - `pip3 install -r requirements.txt`
5. ???
6. Profit

Using Testdata
--------
In order to simplify development for all, we have included a test fixture.
Using `testserver` will delete the data after running.
To use it do the following:
1. `python manage.py migrate`
2. `python manage.py testserver stregsystem/fixtures/testdata.json`
3. ???
4. Profit

Admin panel: <http://127.0.0.1:8000/admin/>  
Login: `tester:treotreo`

Stregsystem: <http://127.0.0.1:8000/1/>  
User: `tester`

Persistent Testdata
-------
Using `runserver` will automatically reload django on code change, and persist data in the database configured in `local.cfg` (can be whatever backend you want to use).
First time:
1. `python manage.py migrate`
2. `python manage.py loaddata stregsystem/fixtures/testdata.json`
3. `python manage.py runserver`
4. ???
5. Profit

From then on
1. `python manage.py runserver`
2. ???
3. Profit
