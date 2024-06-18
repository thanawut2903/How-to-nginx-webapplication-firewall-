# How-to-nginx-webapplication-firewall-

# 1.Install Nginx 

https://docs.nginx.com/nginx/admin-guide/installing-nginx/installing-nginx-open-source/

# Installing a Prebuilt Ubuntu Package from an Ubuntu Repository

#sudo apt-get update

#sudo apt-get install nginx

#sudo nginx -v

# Installing a Prebuilt Ubuntu Package from the Official NGINX Repository

#sudo apt install curl gnupg2 ca-certificates lsb-release ubuntu-keyring

#curl https://nginx.org/keys/nginx_signing.key | gpg --dearmor \
| sudo tee /usr/share/keyrings/nginx-archive-keyring.gpg >/dev/null

#gpg --dry-run --quiet --no-keyring --import --import-options import-show /usr/share/keyrings/nginx-archive-keyring.gpg

#gpg --dry-run --quiet --no-keyring --import --import-options import-show /usr/share/keyrings/nginx-archive-keyring.gpg

#pub   rsa2048 2011-08-19 [SC] [expires: 2024-06-14]
  573BFD6B3D8FBC641079A6ABABF5BD827BD9BF62
uid                      nginx signing key <signing-key@nginx.com>

#echo "deb [signed-by=/usr/share/keyrings/nginx-archive-keyring.gpg] \
http://nginx.org/packages/ubuntu `lsb_release -cs` nginx" \
    | sudo tee /etc/apt/sources.list.d/nginx.list

#echo "deb [signed-by=/usr/share/keyrings/nginx-archive-keyring.gpg] \
http://nginx.org/packages/mainline/ubuntu `lsb_release -cs` nginx" \
    | sudo tee /etc/apt/sources.list.d/nginx.list

#echo -e "Package: *\nPin: origin nginx.org\nPin: release o=nginx\nPin-Priority: 900\n" \
    | sudo tee /etc/apt/preferences.d/99nginx

#sudo apt update

#sudo apt install nginx

#sudo nginx

#curl -I 127.0.0.1
HTTP/1.1 200 OK
Server: nginx/1.27.0


# 2.Comply Libmodsecurity ตัวแชร์ไลบรารี่ที่ modsecurity ต้องการ

sudo apt install -y apt-utils autoconf automake build-essential git libcurl4-openssl-dev \
libgeoip-dev libmdb-dev libpcre3-dev libtool libxml2-dev libyajl-dev pkg-config wget zlib1g-dev

#git clone --depth 1 -b v3/master --single-branch https://github.com/SpiderLabs/ModSecurity 

#cd ModSecurity

#git submodule init

#git submodule update

#sudo apt-get install libtool

#sudo apt-get install libpcre3-dev

#sudo ./build.sh

#sudo ./configure

#sudo apt install make

#sudo make

#sudo make install

3.Comply modsecurity ให้ nginx ใช้งาน

#cd

#wget https://nginx.org/download/nginx-1.21.1.tar.gz ////(version ต้องตรงกับ nginx ของเรา เช็ค version โดยคำสั่ง nginx -V)////

![image](https://github.com/thanawut2903/How-to-nginx-webapplication-firewall-/assets/159118913/c5f90260-f432-48c5-b383-41e9f40421f7)

#tar xvfz nginx-1.21.1.tar.gz

#cd nginx-1.21.1/

#wget https://github.com/SpiderLabs/ModSecurity-nginx/releases/download/v1.0.3/modsecurity-nginx-v1.0.3.tar.gz

#tar xvfz modsecurity-nginx-v1.0.3.tar.gz

#sudo apt-get install zlib1g-dev

#./configure --add-dynamic-module=./modsecurity-nginx-v1.0.3 --with-compat

#sudo make modules

#sudo cp objs/ngx_http_modsecurity_module.so /etc/nginx/modules

https://docs.nginx.com/nginx/admin-guide/installing-nginx/installing-nginx-open-source/

sudo apt-get install -y apt-utils autoconf automake build-essential git libcurl4-openssl-dev \
libgeoip-dev libmdb-dev libpcre++-dev libtool libxml2-dev libyajl-dev pkgconf wget zlib1g-dev

sudo apt install -y apt-utils autoconf automake build-essential git libcurl4-openssl-dev \
libgeoip-dev libmdb-dev libpcre3-dev libtool libxml2-dev libyajl-dev pkg-config wget zlib1g-dev

