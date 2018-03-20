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
