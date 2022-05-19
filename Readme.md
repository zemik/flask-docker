https://github.com/Dev-Elie/Flask-Docker-App/blob/main/README.md
https://www.freecodecamp.org/news/how-to-dockerize-a-flask-app/

python3 -m venv venv
The virtual environment was not created successfully because ensurepip is not
available.  On Debian/Ubuntu systems, you need to install the python3-venv
package using the following command.

    apt install python3.10-venv

You may need to use sudo with that command.  After installing the python3-venv
package, recreate your virtual environment.

Failing command: ['/home/zmk/workspace/flask-docker/venv/bin/python3', '-Im', 'ensurepip', '--upgrade', '--default-pip']

sudo apt install python3.10-venv

pip install flask                   
zsh: command not found: pip

sudo apt install python3-pip

source venv/bin/activate
source: Нет такого файла или каталога: venv/bin/activate

docker docker build --tag python-docker .


docker build --tag python-docker .
Sending build context to Docker daemon  21.02MB
Step 1/6 : FROM python:3.9.2
3.9.2: Pulling from library/python
004f1eed87df: Pull complete 
5d6f1e8117db: Pull complete 
48c2faf66abe: Pull complete 
234b70d0479d: Pull complete 
6fa07a00e2f0: Pull complete 
04a31b4508b8: Pull complete 
1823d93d9698: Pull complete 
2eee1b8e2538: Pull complete 
b48672c0140e: Pull complete 
Digest: sha256:d5d25f8ddcf983c0164bdcdc87b330d31417e2ce302dbd3e1d0e90fddf3ddff1
Status: Downloaded newer image for python:3.9.2
 ---> 587b1bc803b3
Step 2/6 : WORKDIR python-docker
 ---> Running in 6d2fc085a898
Removing intermediate container 6d2fc085a898
 ---> aa941baede70
Step 3/6 : COPY requirements.txt requirements.txt
 ---> 302391253820
Step 4/6 : RUN pip3 install -r requirements.txt
 ---> Running in fd85ff54d002
WARNING: You are using pip version 21.0.1; however, version 22.1 is available.
You should consider upgrading via the '/usr/local/bin/python -m pip install --upgrade pip' command.
Removing intermediate container fd85ff54d002
 ---> cb9f28063281
Step 5/6 : COPY . .
 ---> 530977968431
Step 6/6 : CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0"]
 ---> Running in e1548fb79337
Removing intermediate container e1548fb79337
 ---> 9cd00598f306
Successfully built 9cd00598f306
Successfully tagged python-docker:latest


docker build --tag python-docker .
Sending build context to Docker daemon  21.02MB
Step 1/6 : FROM python:3.9.2
3.9.2: Pulling from library/python
004f1eed87df: Pull complete 
5d6f1e8117db: Pull complete 
48c2faf66abe: Pull complete 
234b70d0479d: Pull complete 
6fa07a00e2f0: Pull complete 
04a31b4508b8: Pull complete 
1823d93d9698: Pull complete 
2eee1b8e2538: Pull complete 
b48672c0140e: Pull complete 
Digest: sha256:d5d25f8ddcf983c0164bdcdc87b330d31417e2ce302dbd3e1d0e90fddf3ddff1
Status: Downloaded newer image for python:3.9.2
 ---> 587b1bc803b3
Step 2/6 : WORKDIR python-docker
 ---> Running in 6d2fc085a898
Removing intermediate container 6d2fc085a898
 ---> aa941baede70
Step 3/6 : COPY requirements.txt requirements.txt
 ---> 302391253820
Step 4/6 : RUN pip3 install -r requirements.txt
 ---> Running in fd85ff54d002
WARNING: You are using pip version 21.0.1; however, version 22.1 is available.
You should consider upgrading via the '/usr/local/bin/python -m pip install --upgrade pip' command.
Removing intermediate container fd85ff54d002
 ---> cb9f28063281
Step 5/6 : COPY . .
 ---> 530977968431
Step 6/6 : CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0"]
 ---> Running in e1548fb79337
Removing intermediate container e1548fb79337
 ---> 9cd00598f306
Successfully built 9cd00598f306
Successfully tagged python-docker:latest


source venv/bin/activate

(venv) ➜  flask-docker python -m pip install --upgrade pip
Requirement already satisfied: pip in ./venv/lib/python3.10/site-packages (22.0.2)
Collecting pip
  Downloading pip-22.1-py3-none-any.whl (2.1 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 2.1/2.1 MB 914.1 kB/s eta 0:00:00
Installing collected packages: pip
  Attempting uninstall: pip
    Found existing installation: pip 22.0.2
    Uninstalling pip-22.0.2:
      Successfully uninstalled pip-22.0.2
Successfully installed pip-22.1

docker run python-docker
/usr/local/bin/python3: No module named flask

nano Dockerfile

nano requirements.txt 

docker docker build --tag python-docker . 
Sending build context to Docker daemon  22.16MB
Step 1/6 : FROM python:3.9.2
 ---> 587b1bc803b3
Step 2/6 : WORKDIR python-docker
 ---> Using cache
 ---> aa941baede70
Step 3/6 : COPY requirements.txt requirements.txt
 ---> 6c64dffdda9c
Step 4/6 : RUN pip3 install -r requirements.txt
 ---> Running in 92d8285b68b5
Collecting click==8.0.3
  Downloading click-8.0.3-py3-none-any.whl (97 kB)
Collecting Flask==2.0.2
  Downloading Flask-2.0.2-py3-none-any.whl (95 kB)
Collecting itsdangerous==2.0.1
  Downloading itsdangerous-2.0.1-py3-none-any.whl (18 kB)
Collecting Jinja2==3.0.2
  Downloading Jinja2-3.0.2-py3-none-any.whl (133 kB)
Collecting MarkupSafe==2.0.1
  Downloading MarkupSafe-2.0.1-cp39-cp39-manylinux_2_5_x86_64.manylinux1_x86_64.manylinux_2_12_x86_64.manylinux2010_x86_64.whl (30 kB)
Collecting Werkzeug==2.0.2
  Downloading Werkzeug-2.0.2-py3-none-any.whl (288 kB)
Installing collected packages: MarkupSafe, Werkzeug, Jinja2, itsdangerous, click, Flask
Successfully installed Flask-2.0.2 Jinja2-3.0.2 MarkupSafe-2.0.1 Werkzeug-2.0.2 click-8.0.3 itsdangerous-2.0.1
WARNING: You are using pip version 21.0.1; however, version 22.1 is available.
You should consider upgrading via the '/usr/local/bin/python -m pip install --upgrade pip' command.
Removing intermediate container 92d8285b68b5
 ---> e87d49c884dd
Step 5/6 : COPY . .
 ---> 8da114ab0c6d
Step 6/6 : CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0"]
 ---> Running in a3af88368480
Removing intermediate container a3af88368480
 ---> 426d7d806539
Successfully built 426d7d806539
Successfully tagged python-docker:latest
➜  flask-docker docker run python-docker         
 * Environment: production
   WARNING: This is a development server. Do not use it in a production deployment.
   Use a production WSGI server instead.
 * Debug mode: off
 * Running on all addresses.
   WARNING: This is a development server. Do not use it in a production deployment.
 * Running on http://172.17.0.2:5000/ (Press CTRL+C to quit)
172.17.0.1 - - [19/May/2022 13:45:20] "GET / HTTP/1.1" 200 -
172.17.0.1 - - [19/May/2022 13:45:20] "GET /favicon.ico HTTP/1.1" 404 -
