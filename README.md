# How-to-nginx-webapplication-firewall-
1.Install Nginx 

#sudo apt update -y

#sudo apt install -y curl gnupg2 ca-certificates lsb-release

#echo "deb http://nginx.org/packages/ubuntu `lsb_release -cs' nginx" | \

sudo tee /etc/apt/sources.list.d/nginx.list

#echo "deb http://nginx.org/packages/mainline/ubuntu lsb_release -cs` nginx" | \

sudo tee /etc/apt/sources.list.d/nginx.list

#echo -e "Package: *\nPin: origin nginx.org\nPin: release o-nginx\nPin-Priority: 900\n" | X sudo tee /etc/apt/preferences.d/99nginx

#curl -o /tmp/nginx_signing.key

#sudo mv /tmp/nginx_signing.key

#sudo apt update -y

#sudo apt install -y nginx

https://nginx.org/keys/nginx_signing.key /etc/apt/trusted.gpg.d/nginx_signing.asc

2.Comply Libmodsecurity ตัวแชร์ไลบรารี่ที่ modsecurity ต้องการ

#sudo apt-get install -y apt-utils autoconf automake build-essential git libcur14-openssl-dev \ libgeoip-dev liblmdb-dev libpcre++-dev libtool libxml2-dev libyajl-dev pkgconf wget zlib1g-dev 

#git clone --depth 1 -b v3/master --single-branch https://github.com/SpiderLabs/ModSecurity 

#cd ModSecurity

#git submodule init

#git submodule update

#./build.sh

#./configure

#make

#sudo make install

3.Comply modsecurity ให้ nginx ใช้งาน

#cd

#wget https://nginx.org/download/nginx-1.21.1.tar.gz ////(version ต้องตรงกับ nginx ของเรา เช็ค version โดยคำสั่ง nginx -V)////

![image](https://github.com/thanawut2903/How-to-nginx-webapplication-firewall-/assets/159118913/c5f90260-f432-48c5-b383-41e9f40421f7)

#tar xvfz nginx-1.21.1.tar.gz

#cd nginx-1.21.1/

#wget https://github.com/Spider Labs/ModSecurity-nginx/releases/download/v1.0.2/modsecurity-nginx- v1.0.2.tar.gz

#tar xvfz modsecurity-nginx-v1.0.2.tar.gz

#./configure --add-dynamic-module=./modsecurity-nginx-v1.0.2 --with-compat

#make modules

#sudo cp objs/ngx_http_modsecurity_module.so /etc/nginx/modules

