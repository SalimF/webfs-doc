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
## change mime type 
mime type setting on the file 
 /etc/mime.types
## the excutable file pathe is 
 /usr/bin/webfsd
 ## make webfs share any folder contents 
 webfs can immpidatly give any folder files public access if you run it inside any folder 

   webfsd   -p 80
 
