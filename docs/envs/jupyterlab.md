### 주피터랩(JupyterLab)을 써볼까요???  
참고(설치) : https://github.com/jupyterlab/jupyterlab  
  
참고(활용) : http://jupyterlab.readthedocs.io/en/latest/  
* 본 문서는 윈도우10에 설치된 아나콘다를 기준으로 작성되었습니다.  

아나콘다(Anaconda)가 설치되어야 합니다.  
  
![주피터랩](./imgs/jupyterlab.jpg)  
  
  
아나콘다 환경(Anaconda Prompt)를 실행하고 주피터 노트북(Jupyter Notebook) 버전을 확인합니다.  
(4.3 이후 버전이어야 합니다.)  
~~~
(E:\Program\Anaconda3) C:\Users\~>jupyter notebook --version
5.0.0
~~~
설치는 쉽습니다.
~~~
(E:\Program\Anaconda3) C:\Users\~>conda clean --index-cache

(E:\Program\Anaconda3) C:\Users\~>conda install -c conda-forge jupyterlab
Fetching package metadata ...............
Solving package specifications: .

Package plan for installation in environment E:\Program\Anaconda3:

The following NEW packages will be INSTALLED:

    ca-certificates:     2018.1.18-0           conda-forge
    jupyterlab:          0.31.10-py36_1        conda-forge
    jupyterlab_launcher: 0.10.5-py36_0         conda-forge
    vc:                  14-0                  conda-forge

The following packages will be UPDATED:

    conda:               4.3.27-py36hcbae3bd_0             --> 4.3.34-py36_0 conda-forge
    openssl:             1.0.2l-vc14_0                     --> 1.0.2n-vc14_0 conda-forge [vc14]

The following packages will be SUPERSEDED by a higher-priority channel:

    conda-env:           2.6.0-h36134e3_1                  --> 2.6.0-0       conda-forge

Proceed ([y]/n)?
~~~
y를 입력하면 설치가 진행됩니다.  
~~~
Proceed ([y]/n)? y

ca-certificate 100% |###############################| Time: 0:00:02  71.65 kB/s
conda-env-2.6. 100% |###############################| Time: 0:00:00 517.28 kB/s
openssl-1.0.2n 100% |###############################| Time: 0:00:05 956.10 kB/s
vc-14-0.tar.bz 100% |###############################| Time: 0:00:00 491.66 kB/s
conda-4.3.34-p 100% |###############################| Time: 0:00:01 545.57 kB/s
jupyterlab_lau 100% |###############################| Time: 0:00:00   5.74 MB/s
jupyterlab-0.3 100% |###############################| Time: 0:00:11   1.06 MB/s

(E:\Program\Anaconda3) C:\Users\~>
~~~

~~~
(E:\Program\Anaconda3) C:\Users\~>conda list | find "ote"
notebook                  5.0.0                    py36_0

(E:\Program\Anaconda3) C:\Users\~>jupyter serverextension enable --py jupyterlab --sys-prefix
Enabling: jupyterlab
- Writing config: E:\Program\Anaconda3\etc\jupyter
    - Validating...
      jupyterlab  ok

(E:\Program\Anaconda3) C:\Users\~>jupyter lab
[I 10:55:44.345 LabApp] The port 8888 is already in use, trying another port.
[I 10:55:44.376 LabApp] JupyterLab beta preview extension loaded from E:\Program\Anaconda3\lib\site-packages\jupyterlab
[I 10:55:44.377 LabApp] JupyterLab application directory is E:\Program\Anaconda3\share\jupyter\lab
[I 10:55:45.295 LabApp] Serving notebooks from local directory: C:\Users\~
[I 10:55:45.295 LabApp] 0 active kernels
[I 10:55:45.295 LabApp] The Jupyter Notebook is running at: http://localhost:8889/?token=blah~
[I 10:55:45.296 LabApp] Use Control-C to stop this server and shut down all kernels (twice to skip confirmation).
[C 10:55:45.300 LabApp]

    Copy/paste this URL into your browser when you connect for the first time,
    to login with a token:
        http://localhost:8889/?token=blah~
[I 10:55:46.039 LabApp] Accepting one-time-token-authenticated connection from ::1
[W 10:55:46.667 LabApp] 404 GET /favicon.ico (::1) 111.14ms referer=None
[I 10:55:48.190 LabApp] Build is up to date
~~~
종료하려면 "Ctrl + C"하면 됩니다.
~~~
[I 10:56:45.300 LabApp] Interrupted...
[I 10:56:45.301 LabApp] Shutting down kernels

(E:\Program\Anaconda3) C:\Users\~>
~~~
