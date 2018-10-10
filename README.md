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
```
$ python3
```

then you can see REPL interface on your CUI window shown below.

```
[ ~/Desktop/python3-tutorial ] $ python3
Python 3.6.6 (default, Oct 10 2018, 23:10:06) [C] on sunos5
Type "help", "copyright", "credits" or "license" for more information.
>>> 
```

Type:

```
>>> print("Hello World.")
```

Then you can see the results after the program line immediatelly like:

```
>>> print("Hello World.")
Hello World.
```

In this REPL environment, you can check your code correct.
If you are worried about the correctness of your code, then you should check the output of your code in this.




