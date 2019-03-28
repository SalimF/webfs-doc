# webfs-doc
document to install webfs simple light weight web server 

# installation 

Debian/Ubuntu  

apt install webfs   

Redhat/CentOS/Fedora

yum install webfs   

### to start webfs type 

service  webfs rstart  

### Stop the server 

service  webfs stop 

# the configuration file 
you can edit webfs setting "e.g chang root folder"

nano /etc/webfsd.conf

Important setting to change in webfsd.conf 
### Change the defult port 
so it will listing to port 80(default wweb browsers port)

web_port="80" 
##  cnage document root
web_root="/var/www"
##  rest of settings 
   web_index=index.html
   
   web_host=
   
   web_ip=
   
   web_port=
   
   web_virtual=false
   
   web_timeout=
   
   web_conn=5000
   
   web_dircache=
   
   web_accesslog=
   
   web_syslog=false
   
   web_user=www-data
   
   web_group=www-data

## change mime type 
mime type setting on the file 
 /etc/mime.types

Example here 
 https://www.apt-browse.org/browse/debian/jessie/main/all/mime-support/3.58/file/etc/mime.types
 
## the excutable file pathe is 
 /usr/bin/webfsd
 
##  webfsd CMD 

	-p port
	   Listen on  Port <>port<> for incoming connections e.g -p 80

	-R dir 
	  document root to <>dir<> and chroot to <>dir<>  e.g -R  /var/www

	-c n
	 seet n number of arreler connection e.g 5000
	-j
	 prevent directory listing if the index-file isn't found
	-e sec
	Expire documents after <>sec<> seconds. Webfsd will send
	a Expires: header set to last-modified time plus <>sec<> seconds 
	e.g   -e 2592000    (expiration = month )
	
	-y n
	  Set the number of threads to spawn (if compiled with thread support).

	 -m file
	   Read mime types from <>file<> .  Default is /etc/mime.types

	 -f file
	 Use <>file<> as index file for directories

	-n hostname
	Set the host  name which the server should use  e.g  -n example.com

	-i ip
	Bind to IP-address <>ip<> e.g  -i  104.16.3.71

	-l log
	Log all requests to the logfile <>log<> e.g -l /etc/webfs.log

	-u user
	Set uid to <>user<> e.g  -u  www-data

	-g group
	Set gid to <>group<>   e.g  -g www-data

 ## make webfs share any folder contents 
 webfs can immpidatly give any folder files public access if you run it inside any folder 
	webfsd   -p 80

# Full example 
	webfsd -p 80 -R  /var/www -c 5000 -e 2592000 -u www-data -g www-data -l /etc/webfs.log   

 
