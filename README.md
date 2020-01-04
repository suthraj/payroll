# Project Title

Simple payroll web application that takes uploaded csv files with predefined formats and calculates payroll per employee per pay period.

## Getting Started


### Prerequisites

Application built and tested in the following environments
* LINUX Ubuntu ( 16.04 / 18.04 )
* Tested with Python versions 2.7.12 / 2.7.15+
* Built using Flask

Update Linux (Ubuntu)

```bash
sudo apt-get update        
sudo apt-get upgrade       
sudo apt-get dist-upgrade  
```

### Installation

A step by step series of examples that tell you how to get a development env running

<b> GIT - Install Git </b>

```bash
#Install git
sudo apt install git
```

<b> DATABASE - Install/Configure MySQL </b>

Install MySQL

```bash
sudo apt-get install mysql-server
```

Login into MySQL

```bash
sudo mysql -p -u root
```

Create following database

```mysql
CREATE DATABASE  payroll;
```

Check if new 'payroll' database has been created

```mysql
SHOW DATABASES;
```

Add following db user access to new database

```mysql
CREATE USER 'srpub'@'localhost' IDENTIFIED BY 'mysql111';
GRANT ALL PRIVILEGES ON payroll.* TO 'srpub'@'localhost';
```

NOTE: If you get password 'current policy requirements' violation error, lower the password policy to 'LOW' as follows:

```mysql
SHOW VARIABLES LIKE 'validate_password%';
SET GLOBAL validate_password_policy=LOW;
```


Double check new user <i> suthraj </i> has access to <i> payroll </i> database

```mysql
SHOW GRANTS FOR 'srpub'@'localhost';
```

<b> PYTHON - Install/Configure Python </b>

Install the following Python packages

```python
sudo apt-get install python-dev
sudo apt-get install python-pip python-virtualenv
```

Check installed Python version, should say "Python 2.7.1x"

```python
python --version
```

Create a directory called vEnvPython in the home directory

```python
mkdir ~/vEnvPy
```

Check Python installation
 
```python
#Check Python installation path (should be: '/usr/bin/python')
which python

#Check Python Virtual Environment installation path (should be: '/usr/bin/virtualenv')
which virtualenv 
```

Create environment variable using Python 2.7

```python
virtualenv ~/vEnvPy/payroll_py2_7 --python=/usr/bin/python

#Activate new python virtual environment
source ~/vEnvPy/payroll_py2_7/bin/activate
```

<b> FLASK - Install/Configure Flask </b>

Install following necessary dependencies

```python
sudo apt-get install python-dev default-libmysqlclient-dev libssl-dev

#Make sure the following dependency is installed successfully (might require 'sudo')
pip install flask-mysqldb
```

Navigate to project directory
Execute provided 'Requirements.txt' file to install all necessary Python dependancies to run the 'Payroll Report' application 
(NOTE: within activated virtual env)

```python
pip install -r requirements.txt
```

## Usage

```python

```



## Running the tests

Explain how to run the automated tests for this system

To run specific test case classes, execute the relevant unit test class one level above the project package parent directory as follows

```bash
~/projects$ python -m unittest -v payroll.web_app.tests.un.classesTC_un.TC_ComputePayroll
```
 
## Deployment

##Troubleshooting

Incomplete termination of previous instance(s) of web app

```python
#Check if multiple processes of the app are active
ps aux | grep "main"

#Kill unwanted instances of web app
kill [process-id]

```

## Built With

* [Flask](http://flask.palletsprojects.com/en/1.1.x/) - The web framework used


## Authors

* **Sutharsan Rajaratnam** - *Project owner & primary contributor* - [servo00](https://github.com/servo00)


## General Comments 
 - Leverages Bootstrap CSS framework, some custom CSS and Javascript.
 - Uses Python 'unittest' test framework 

 
## Acknowledgments

