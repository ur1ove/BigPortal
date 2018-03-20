### Python | How to make my workspaces as python versions
!) Python 2.7    
envtester@DataLX01:~$ virtualenv --python=python2.7 myPython2.7  
~~~
Running virtualenv with interpreter /usr/bin/python2.7
New python executable in /home/envtester/myPython2.7/bin/python2.7
Also creating executable in /home/envtester/myPython2.7/bin/python
Installing setuptools, pkg_resources, pip, wheel...done.
~~~
envtester@DataLX01:~$ source myPython2.7/bin/activate  
(myPython2.7) envtester@DataLX01:~$ python -V
~~~
Python 2.7.12
~~~
(myPython2.7) envtester@DataLX01:~$ deactivate  
2) Python 3.6
envtester@DataLX01:~$ virtualenv --python=python3.5 myPython3.5  
~~~
Running virtualenv with interpreter /usr/bin/python3.5
Using base prefix '/usr'
New python executable in /home/envtester/myPython3.5/bin/python3.5
Also creating executable in /home/envtester/myPython3.5/bin/python
Installing setuptools, pkg_resources, pip, wheel...done.
~~~
envtester@DataLX01:~$ source myPython3.5/bin/activate  
~~~
(myPython3.5) envtester@DataLX01:~$ python -V  
~~~
Python 3.5.2
~~~
(myPython3.5) envtester@DataLX01:~$ deactivate
~~~
envtester@DataLX01:~$ mkdir ~/.python_virtual_envs  
envtester@DataLX01:~$ vi ~/.bashrc  
~~~
export WORKON_HOME=~/.python_virtual_envs
source /usr/local/bin/virtualenvwrapper.sh
~~~
  
root@DataLX01:~# su - envtester  
~~~
/usr/bin/python: No module named virtualenvwrapper
virtualenvwrapper.sh: There was a problem running the initialization hooks.

If Python could not import the module virtualenvwrapper.hook_loader,
check that virtualenvwrapper has been installed for
VIRTUALENVWRAPPER_PYTHON=/usr/bin/python and that PATH is
set properly.
~~~
### 소프트웨어 설치  
root@DataLX01:~# pip install virtualenv  
~~~
Requirement already satisfied: virtualenv in /usr/lib/python3/dist-packages
~~~
root@DataLX01:~# pip install virtualenvwrapper  
~~~
Collecting virtualenvwrapper
  Downloading virtualenvwrapper-4.8.2-py2.py3-none-any.whl
Collecting virtualenv-clone (from virtualenvwrapper)
  Downloading virtualenv_clone-0.3.0-py2.py3-none-any.whl
Collecting stevedore (from virtualenvwrapper)
  Downloading stevedore-1.28.0-py2.py3-none-any.whl
Requirement already satisfied: virtualenv in /usr/lib/python3/dist-packages (from virtualenvwrapper)
Collecting pbr!=2.1.0,>=2.0.0 (from stevedore->virtualenvwrapper)
  Downloading pbr-3.1.1-py2.py3-none-any.whl (99kB)
    100% |████████████████████████████████| 102kB 1.8MB/s 
Requirement already satisfied: six>=1.10.0 in /usr/local/lib/python3.6/dist-packages (from stevedore->virtualenvwrapper)
Installing collected packages: virtualenv-clone, pbr, stevedore, virtualenvwrapper
Successfully installed pbr-3.1.1 stevedore-1.28.0 virtualenv-clone-0.3.0 virtualenvwrapper-4.8.2
~~~
