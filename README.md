# goaccess-installation-on-centos8
cd /usr/src  
wget https://tar.goaccess.io/goaccess-1.5.1.tar.gz  
tar zxvf goaccess-1.5.1.tar.gz   
cd goaccess-1.5.1   
yum install gcc perl make  
yum -y --enablerepo=epel install geoip  install mod_geoip GeoIP GeoIP-devel GeoIP-data zlib-devel  
sudo yum install GeoIP GeoIP-devel  
sudo yum install ncurses-devel  
./configure --enable-utf8 --enable-geoip=legacy  
make  
make install  
remember to go to config directory to adjust time and report formats  
goaccess /var/log/httpd/access_log --log-format=COMBINED -o /var/www/html/report.html --real-time-html --daemonize  /var/log/nginx/access.log  
http://ip address/report.html
