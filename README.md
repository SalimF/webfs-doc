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
   web_root=/var/ftp
   web_host=
   web_ip=
   web_port=
   web_virtual=false
   web_timeout=
   web_conn=
   web_dircache=
   web_accesslog=
   web_syslog=false
   web_user=www-data
   web_group=www-data

## change mime type 
mime type setting on the file 
 /etc/mime.types
## the excutable file pathe is 
 /usr/bin/webfsd
 ## make webfs share any folder contents 
 webfs can immpidatly give any folder files public access if you run it inside any folder 

   webfsd   -p 80
 
