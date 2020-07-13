# PyBase - DB Manager
![PyBase Logo](./res/pybase-logo.png)

PyBase is a DataBase Manager for JSON, YAML and SQLite.

It's focused on the ease and effectiveness for the administration of databases.

> **PyBase is actually on Beta phase, may contain bugs.**

------

## Why PyBase?
If you want to store static data (JSON, YAML) or store a database in SQLite,
the best thing would be to use an administrator that simplifies your tasks and
helps you with a good organization and efficiently.

PyBase does exactly that, allows you to create such databases with
just one method, and simplifies the task of manipulating their data!

> **PyBase doesn't yet support SQLite, it will be added soon.**

------

# Quick start
## Installation
PyBase requires Python 3.x and can be installed through `pip` with the following command.
```sh
pip install pybase_db
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
pybase_info = {"pybase": "awesomeness", "version": "0.2.0"}

# Lets insert the defined dict inside our database.
db.insert(pybase_info)  #=> {'pybase': 'awesomeness', 'version': '0.2.0'}
print(db.get())

# Lets delete an object inside our database cuz it's useless.
db.delete('pybase')  #=> {'version': '0.2.0'}
print(db.get())

# Lets fetch an object inside our database and display its type.
# It's useful to debug and manipulate the data dynamically.
print(db.fetch('version'))

#Gets the corresponding value according to the specified key
print(db.get("version")) #=> '0.2.0'
```

## Documentation
You can see the PyBase documentation through the `help()` function of the REPL
and through the [official documentation site](https://ntbbloodbath.github.io/PyBase).

------

## Contribuitors
- [Danny2105](https://github.com/Danny2105)

## License
**PyBase is distributed under MIT License.**

## Contributing

When contributing to this repository, please first discuss the change you wish to make via issue,
email, or any other method with the owners of this repository before making a change. 

Please note we have a code of conduct, please follow it in all your interactions with the project.

### Pull Request Process

1. Ensure any install or build dependencies are removed before the end of the layer when doing a 
   build.
2. Update the README.md with details of changes to the interface, this includes new environment 
   variables, exposed ports, useful file locations and container parameters.
3. Increase the version numbers in any examples files and the README.md to the new version that this
   Pull Request would represent. The versioning scheme we use is [SemVer](http://semver.org/).
4. You may merge the Pull Request in once you have the sign-off of two other developers, or if you 
   do not have permission to do that, you may request the second reviewer to merge it for you.

## Code of Conduct
You can see the code of conduct [here](./CODE_OF_CONDUCT.md)
