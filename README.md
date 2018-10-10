# SCCP2018 Q3Q4 environment tutorial
m5211143 Tomohiro Saito

11 Oct.

## Objective (Goal)

* Installation of Python3 to your local environment on Univ. of Aizu. (Solaris)
* Create Hello World program on flask framework

## Instllation of Python3
### Instllation
We mainly use python 3.6.6 (latest version of Python3.6.x) in this class, but Solaris and Mac OSX workstation in our university, unfortunatelly, didn't have environment for it.
In this class, we inroduce how to install Python3 to your local environment.

Execute below script:

```sh
$ cd $HOME
$ mkdir -p usr/bin/Python
$ cd usr/bin/Python

$ wget https://www.python.org/ftp/python/3.6.6/Python-3.6.6.tgz
$ tar zxvf Python-3.6.6.tgz
$ cd Python-3.6.6
$ ./configure --without-gcc --prefix=$HOME/usr

$ make
$ make install
$ make clean
```

### Path
The installation has successfully finished, and then you must add command to the environment path on your local environment to execute easilly.
Put above appropriate installation directory according to your shell.

For example, for bash:

```sh
echo "export PATH=\$PATH:$HOME/usr/bin" >> ~/.bash_profile
```

### Hello World
After above process has done, you can launch python3 REPL on your terminal.


Execute:
```sh
$ python3
```

then you can see REPL interface on your CUI window shown below.

```sh
[ ~/Desktop/python3-tutorial ] $ python3
Python 3.6.6 (default, Oct 10 2018, 23:10:06) [C] on sunos5
Type "help", "copyright", "credits" or "license" for more information.
>>> 
```

Type:

```py
>>> print("Hello World.")
```

Then you can see the results after the program line immediatelly like:

```py
>>> print("Hello World.")
Hello World.
```

In this REPL environment, you can check your code correct.
If you are worried about the correctness of your code, then you should check the output of your code in this.


## Flask framework
### Installation of flask
At first, we need to check *pip3* command has installed successfully.
*pip3* command is a package management tool for python3.
We can install any package, in addition to flask, by using this command.
(In detal, see https://ja.wikipedia.org/wiki/Pip)
(pip3 command was automatically installed with python3 installation, but we check this before installation of flask framework just in case.)

```sh
$ pip3
```

then you can see the description about the option of *pip3* command like:

```
Usage:   
  pip3 <command> [options]

Commands:
  install                     Install packages.
  download                    Download packages.
  uninstall                   Uninstall packages.
  freeze                      Output installed packages in requirements format.
  list                        List installed packages.
  show                        Show information about installed packages.
  check                       Verify installed packages have compatible dependencies.
  config                      Manage local and
...
```

If you can check this output after execute *pip3* command, then let's move to installation of flask!
flask framework can be installed with below command:

```
$ pip3 install flask
```

After succesfully finished, create folder for hello world project:

```sh
$ cd $HOME/
$ mkdir -p ./SCCP2018/projects/
$ cd ./SCCP2018/projects/
$ mkdir hello-flask
$ cd hello-flask

$ touch app.py
```

In *app.py*:

```
from flask import Flask

app = Flask(__name__)

@app.route("/")
def hello():
    return "Hello, Flask!"

if __name__ == "__main__":
    app.run()
```

then save the file and go back to the terminal.
Execute:

```
$ python3 app.py
```

then you can see the message from flaks framework like:

```
[ ~/hello-flask ] $ python3 app.py
 * Serving Flask app "app" (lazy loading)
 * Environment: production
   WARNING: Do not use the development server in a production environment.
   Use a production WSGI server instead.
 * Debug mode: off
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
```

Let's focus on the bottom of the message, here is the URL of your application.
On filefox, type above URL, (In this time, we must access to the http://localhost:5000/ to see the application)
Then you can see the word: "Hello World" on your browser.

### Debug mode of flask
If you have changed your code, then you have to terminate your application on the terminal, and then you re-execute the flask with "python3 app.py".
However, it doesn't need to re-start if you use "Debug mode" on your flask.
This function is normally called as "Hot reloading".

If you want to enable debug-mode, then change your code according to below one.

```py
from flask import Flask

app = Flask(__name__)

@app.route("/")
def hello():
    return "Hello, Flask!"

if __name__ == "__main__":
    debug=True
    app.run()
```

Then you can execute the app.

