# Using-HttpsElastic-With-Java
This project is iniciative for Tutorial for install elasticsearch with https certificate. Furthermore this is example using java for connect, write data and search data using data with CSVs and PostgreSQL databases.


# Install Elastic-8

Using Debian 12

Execute this commads as root:

``
apt update
apt upgrade
wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo gpg --dearmor -o /usr/share/keyrings/elasticsearch-keyring.gpg
apt-get install apt-transport-https
echo "deb [signed-by=/usr/share/keyrings/elasticsearch-keyring.gpg] https://artifacts.elastic.co/packages/8.x/apt stable main" | sudo tee /etc/apt/sources.list.d/elastic-8.x.list
apt update
apt-get install elasticsearch
``

# Create self-sign certificate

``
mkdir certificate
cd certificate
openssl req -x509 -newkey rsa:2048 -keyout certificate.key -out certificate.crt -days 3650 -nodes -subj '/CN=elasticdb-8.casa.com.br'
``



