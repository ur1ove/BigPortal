### 주피터허브
참고 : https://github.com/jupyterhub/jupyterhub/wiki/Run-jupyterhub-as-a-system-service

주피터허브를 시스템에 등록해보자.

~~~
condadmin@DataLX01:~$ which jupyterhub
/home/condadmin/anaconda3/bin/jupyterhub
~~~
~~~
sudo vi /etc/systemd/system/jupyterhub.service
~~~
~~~
[Unit]
Description=Jupyterhub
After=syslog.target network.target

[Service]
User=root
Environment="PATH=/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/home/condadmin/anaconda3/bin"
ExecStart=/home/condadmin/anaconda3/bin/jupyterhub -f /etc/jupyterhub/jupyterhub_config.py

[Install]
WantedBy=multi-user.target
~~~
