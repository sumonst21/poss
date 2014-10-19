# POSS - Personal Object Sharing System

## Demo
https://demo.ge1.me  
Email: demo  
Password: demo  
Reset: every hour

## Requirements
* git (for installing/upgrading)
* Python 3.3 or 3.4
* virtualenv
* MySQL Server

## Install
**1)** Clone the project and checkout the latest tag
```
git clone https://github.com/fnkr/POSS.git
git checkout 1.0
cd poss
```

**2)** Set up your environment
```
virtualenv env

# Windows
env\scripts\pip install -r requirements

# Linux
env/bin/pip install -r requirements
```

**3)** Download GeoIP databse (optional)  
Download and extract "GeoLite Country" and "GeoLite Country IPv6" databases
and put the files `GeoIP.dat` and `GeoIPv6.dat` into the main directory.
http://dev.maxmind.com/geoip/legacy/geolite/

**4)** Copy config.dist.py to config.py and modify as needed. Note that POSS has only been tested with MySQL (5.5), everything else may not work.

**5)** Set up the database
```
# Windows
env\scripts\python manage.py db upgrade

# Linux
env/bin/python manage.py db upgrade
```

**6)** Run the server
```
# Windows
env\scripts\python manage.py runserver

# Linux
env/bin/python manage.py runserver
```

## Upgrade

**1)** Fetch and checkout the latest tag
```
git fetch --tags
git checkout 1.0
```

**2)** Migrate the database
```
# Windows
env\scripts\python manage.py db upgrade

# Linux
env/bin/python manage.py db upgrade
```

## Development notes
**-** Run the server in development mode
```
# Windows
env\scripts\python manage.py runserver --debug

# Linux
env/bin/python manage.py runserver --debug
```

**-** Create a migration after you changed the database
```
# Windows
env\scripts\python manage.py db migrate -m "comment"

# Linux
env/bin/python manage.py db migrate -m "comment"
```