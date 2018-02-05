### 주피터허브
참고 : https://github.com/jupyterhub/jupyterhub/wiki/Run-jupyterhub-as-a-system-service

주피터허브를 시스템에 등록해보자.

주피터허브가 설치된 위치를 확인하고
~~~
condadmin@DataLX01:~$ which jupyterhub
/home/condadmin/anaconda3/bin/jupyterhub
~~~
등록할 서비스 이름을 설정한다.
~~~
sudo vi /etc/systemd/system/jupyterhub.service
~~~
내용은 아래와 같이 작성한다.
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
시스템 서비스 목록을 갱신하고 주피터허브를 시작한다.
~~~
condadmin@DataLX01:~$ sudo systemctl daemon-reload
condadmin@DataLX01:~$ sudo systemctl start jupyterhub
~~~
