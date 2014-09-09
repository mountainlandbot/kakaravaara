# Kakaravaara

[Kakaravaara](https://kakaravaara.fi) is a cottage rental site. The code is hosted on [GitHub](https://github.com/jaywink/kakaravaara).

## Tech stack

Built with [Mezzanine](https://github.com/stephenmcd/mezzanine) which is powered by [Django](https://www.djangoproject.com/). A [fork](https://github.com/jaywink/cartridge-reservable) of [Cartridge](https://github.com/stephenmcd/cartridge) is used for the reservations part of the site.

## Installation

Installation example for Ubuntu 13.10. Either do it your preferred way or follow the following guide.

### Prerequisites

#### Database

SQLite can be used for development. For production installations, we can use for example [MariaDB](https://mariadb.org/).

```
sudo apt-get install software-properties-common
sudo apt-key adv --recv-keys --keyserver hkp://keyserver.ubuntu.com:80 0xcbcb082a1bb943db
sudo add-apt-repository 'deb http://mirror.netinch.com/pub/mariadb/repo/10.0/ubuntu saucy main'
sudo apt-get update
sudo apt-get install mariadb-server
```

#### Python

Python 2.7 has been used while developing. Python 3.x might work but no guarantees at the moment. [Pythonz](https://github.com/saghul/pythonz) is a nice Python version manager, though totally *optional*;

`curl -kL https://raw.github.com/saghul/pythonz/master/pythonz-install | bash`

> Please add the following line to the end of your ~/.bashrc:

`[[ -s $HOME/.pythonz/etc/bashrc ]] && source $HOME/.pythonz/etc/bashrc`

#### PIP

PIP needs to be installed;

`sudo easy_install pip`

#### Virtualenvwrapper

Suggested way to do development is to use [virtualenvwrapper](https://pypi.python.org/pypi/virtualenvwrapper).

```
sudo pip install virtualenv virtualenvwrapper
mkdir $HOME/.virtualenvs
```

### Python environment

```
pythonz install -t cpython 2.7.6
mkvirtualenv -p $HOME/.pythonz/pythons/CPython-2.7.6/bin/python kakaravaara
```

The environment will be automatically activated. In the future before starting development, do;

`workon kakaravaara`

### Get code

```
cd /path/to/local/git/repos
git clone git@github.com:jaywink/kakaravaara.git
cd kakaravaara
```

### Install packages

`pip install -r requirements/project.txt --allow-external pil --allow-unverified pil`

Some extra args to not be so picky about PIL sources.

A proprietary `kakaravaara-utils` is also required. Ask author, will make it optional soon :P

### Setup application

#### Configuration

`cp local_settings.py.example local_settings.py`

#### DB

```
python manage.py syncdb --all
python manage.py migrate --fake
```

## Running application

You can run the application locally with the following;

`python manage.py runserver`

## Development

*TBD*

## License

BSD
