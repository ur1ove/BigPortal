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
