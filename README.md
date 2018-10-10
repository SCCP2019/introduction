# Python3 install tutorial
m5211143 Tomohiro Saito

11 Oct.

## Objective (Goal)

* Installation of Python3 to your local environment on Univ. of Aizu. (Solaris)
* Create Hello World program on flask framework

## Instllation of Python3
We mainly use python 3.6.6 (latest version of Python3.6.x) in this class.

See below script:

```sh
cd $HOME
mkdir -p usr/bin/Python
cd usr/bin/Python

wget https://www.python.org/ftp/python/3.6.6/Python-3.6.6.tgz
tar zxvf Python-3.6.6.tgz
cd Python-3.6.6
./configure --without-gcc --prefix=$HOME/usr
make
make install
make clean
```

After the installation has successfully finished, you must consider about the environment 'path' on your local environment to execute it.
Add above appropriate installation directory according to your shell.

For example, for bash:

```sh
echo "export PATH=\$PATH:$HOME/usr/bin" >> ~/.bash_profile
```
