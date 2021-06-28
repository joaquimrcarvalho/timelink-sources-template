# Notebooks

This folder contains Jupyter notebooks that interact with the MHK/Timelink database to process data in forms not available using the web interface.

To be able to run notebooks you need to install the Python VSCode extension and a Python interpreter on the current machine.

## Install the Python instruction and the Python interpreter

To install the Python extension at https://marketplace.visualstudio.com/items?itemName=ms-python.python

## Install the SQL extension for notebooks

Open the terminal in VSCode: Command+j or menu `Terminal` -> `New terminal`

Type 

     ``pip install ipython-sql `[return]` ``

When finished install the Mysql connector


    ``pip install mysql-connector-python`´


## Install auxiliary packages

Reading MHK configuration files 

    ``pip install python-dotenv``

Data analysis with Pandas

    ``pip install pandas``

Widgets for interaction with user

    ``pip install ipywidgets``
## References

* https://pypi.org/project/ipython-sql/
* https://pypi.org/project/python-dotenv/
* https://pypi.org/project/mysql-connector-python/
* https://pandas.pydata.org
* https://ipywidgets.readthedocs.io/en/latest/index.html