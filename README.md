**PACKAGE AND VERSIONS REQUIRED**

1) **pip3**	- 23.0.2 from /usr/lib/python3/dist-packages/pip (python 3.10)
2) **pip** - 23.0.2 from /usr/lib/python3/dist-packages/pip (python 3.10)
3) **pythonn** -	3.11.4
4) **node** -	20.17.0
5) **npm**	- 9.8.1
6) **mariadb** -	Ver 15.1 Distrib 10.6.7-MariaDB
7) **yarn**	- 1.22.19
8) **/opt/bench/node_modules/.bin/node-sass** - node-sass 9.0.1 (Wrapper) [JavaScript] libsass 3.5.5 (Sass Compiler) [C/C++] npm node-sass	8.19.1
9) **pip3**	- 23.0.2 from /usr/lib/python3/dist-packages/pip (python 3.10)
10) **pip**	- 23.0.2 from /usr/lib/python3/dist-packages/pip (python 3.10)
11) **redis-server** -	Redis server v=7.0.16 sha=00000000:0 malloc=jemalloc-5.2.1 bits=64 build=a3fdef44459b3ad6
12) **wkhtmltopdf**	- 0.12.6
13) **git** -	2.39.1

**STEP 1 Install git**

     sudo apt-get install git

**STEP 2 install python-dev**

     sudo apt-get install python3-dev

**STEP 3 Install setuptools and pip (Python's Package Manager)**

     sudo apt-get install python3-setuptools python3-pip
	 
**STEP 4 Install virtualenv**

     sudo apt-get install virtualenv
	 
**CHECK PYTHON VERSION**

     python3 -V
	 
**IF VERSION IS 3.8.X RUN**

    sudo apt install python3.8-venv
	
**IF VERSION IS 3.10.X RUN**

    sudo apt install python3.10-venv
	
**STEP 5 Install MariaDB**

    sudo apt-get install software-properties-common
	
    sudo apt install mariadb-server
	
    sudo mysql_secure_installation
	
**STEP 6 MySQL database development files**

    sudo apt-get install libmysqlclient-dev
	
**STEP 7 Edit the mariadb configuration ( unicode character encoding )**

     sudo nano /etc/mysql/mariadb.conf.d/50-server.cnf
**add this to the 50-server.cnf file**

    [server]
    user = mysql
     pid-file = /run/mysqld/mysqld.pid
     socket = /run/mysqld/mysqld.sock
     basedir = /usr
     datadir = /var/lib/mysql
     tmpdir = /tmp
     lc-messages-dir = /usr/share/mysql
     bind-address = 127.0.0.1
     query_cache_size = 16M
     log_error = /var/log/mysql/error.log

     [mysqld]
     innodb-file-format=barracuda
     innodb-file-per-table=1
     innodb-large-prefix=1
     character-set-client-handshake = FALSE
     character-set-server = utf8mb4
     collation-server = utf8mb4_unicode_ci      
 
     [mysql]
     default-character-set = utf8mb4
	 
Now press (Ctrl-X) to exit

    sudo service mysql restart

**STEP 8 install Redis**

    sudo apt-get install redis-server
	
**STEP 9 install Node.js 14.X package**

    sudo apt install curl 
    curl https://raw.githubusercontent.com/creationix/nvm/master/install.sh | bash
    source ~/.profile
    nvm install 14.15.0  
	
**STEP 10 install Yarn**

    sudo apt-get install npm

    sudo npm install -g yarn
	
**STEP 11 install wkhtmltopdf**

    sudo apt-get install xvfb libfontconfig wkhtmltopdf
	
**STEP 12 install frappe-bench**

    sudo -H pip3 install frappe-bench

    bench --version

**STEP 13 initilise the frappe bench & install frappe latest version**

    bench init frappe-bench 

    cd frappe-bench/
    bench start
	
**STEP 14 create a site in frappe bench**

    bench yoursitename  dcode.com

    bench use dcode.com
	
**STEP 15 install ERPNext latest version in bench & site**

    bench get-app erpnext --branch version-13
    
###OR

    bench get-app https://github.com/frappe/erpnext --branch version-13

    bench --site dcode.com install-app erpnext

    bench start
**If its not working after STEP 13**

    bench new-site erp.syncbricks.com
you can stop this by pressing ctr + c. Lest us install ERPNext and HRMS.

**Now you need to update the apps to the site**

    bench get-app hrms --branch version-15
    bench --site erp.syncbricks.com install-app erpnext
    bench --site erp.syncbricks.com install-app hrms

**Now you must tell the bench to use erp.syncbricks.com as default site you will use**

    bench use erp.syncbricks.com

      
    




