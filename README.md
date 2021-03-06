![PyBase](https://socialify.git.ci/PyBase/PyBase/image?description=1&descriptionEditable=Python%20DataBase%20Manager%20for%20multiple%20filetypes%20including%20SQLite3.&font=Inter&forks=1&issues=1&logo=https%3A%2F%2Fiili.io%2FFEHkLg.png&pattern=Circuit%20Board&stargazers=1&theme=Light)

[![Netlify Status](https://api.netlify.com/api/v1/badges/6a03656b-b3f4-4a90-a52d-9f8d176d6a28/deploy-status)](https://app.netlify.com/sites/pybase/deploys)
![Python Versions](https://img.shields.io/pypi/pyversions/pybase-db)
![Version](https://img.shields.io/pypi/v/pybase-db?color=green&label=version)
[![Downloads](https://pepy.tech/badge/pybase-db)](https://pepy.tech/project/pybase-db)
[![Discord](https://img.shields.io/discord/779841556215627776?color=008aff&label=support&logo=discord&style=flat-square)](https://discord.gg/4BC8RqYxGc)
![License](https://img.shields.io/pypi/l/pybase-db)

PyBase is focused on the ease and effectiveness for the administration of databases.

> **PyBase is actually on Beta phase, may contain bugs.**

------

## Why PyBase?
**If you want to store static data** (JSON, YAML, Bytes) **or store a database in SQLite,**
**the best thing would be to use an administrator that simplifies your tasks and
helps you with a good organization and efficiently.**

**PyBase does exactly that, allows you to create such databases with
just one method, and simplifies the task of manipulating their data!**

------

## Contribuitors
- [Danny2105](https://github.com/Danny2105)
- [acarkh](https://github.com/acarkh)

------

# Quick start
## Installation
PyBase requires Python 3.x and can be installed through `pip` with the following command.
```sh
# Stable version
python3 -m pip install -U pybase_db

# Pre-release (Development) version
python3 -m pip install -U --pre pybase_db

# From github's latest commit
# Available branches:
#   • master (recommended)
#   • development (unstable releases)
# NOTE: this installation mode will not install PyBase dependencies!
python3 -m pip install -U git+https://github.com/PyBase/PyBase@branch
```

### Building
The development branch changes aren't compiled and uploaded to Pypi every time,
so you must compile a wheel yourself to test the experimental stuff if the newest
changes aren't uploaded to Pypi.
```sh
python3 setup.py bdist_wheel

python3 -m pip install -U dist/pybase_db-version-py3-none-any.whl
```

## Usage example
This is a brief example of the methods that PyBase currently has.
```py
# Lets import PyBase Class from PyBase Package
from pybase import PyBase

# Lets define our database name and format (with default db_path).
# db_type isn't case sensitive. You can use JSON and json and it'll be valid.
db = PyBase("example", "JSON")  #=> ./example.json

# Lets define and add some content to our database.
pybase_info = {"pybase": "awesomeness", "version": "0.3.0"}

# Lets insert the defined dict inside our database.
db.insert(pybase_info)  #=> {'pybase': 'awesomeness', 'version': '0.3.0'}
print(db.get())

# Lets delete an object inside our database cuz it's useless.
db.delete('pybase')  #=> {'version': '0.3.0'}
print(db.get())

# Lets fetch an object inside our database and display its type.
# It's useful to debug and manipulate the data dynamically.
print(db.fetch('version'))

#Gets the corresponding value according to the specified key
print(db.get("version")) #=> '0.3.0'
```

> **To see SQLite3 usage example, click [here](./examples/pysql_usage.py)**

## Documentation
You can see the PyBase documentation through the `help()` function of the REPL
and through the [official documentation site](https://pybase.netlify.app/docs/).

------

## License
**PyBase is distributed under MIT License.**

## Contributing
You can see how to contribute [here](./CONTRIBUTING.md)

## Code of Conduct
You can see the code of conduct [here](./CODE_OF_CONDUCT.md)
