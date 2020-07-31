# Nginx reverse proxy

## Nginx
- Nginx is an open source high performance web server, that powers many modern web application
- Nginx is effective at serving static content, integrates with other applications to deliver dynamic sites, and can also function as a load-balancer(efficient distribution of network/application)

## Reverse proxy
- A server that sits in front of web servers and forwards clients requests(e.g. web browser) to those web servers
- Reverse proxies are typically implemented to help increase security, performance and reliability.

## The Project
- Currently we are running an application on port 3000, however if we want to make this accessible to the client, the application should be available on port 80. Port 3000 should be used in the development process and not for final deployment.
- The task is to automate the connection from port 3000 to port 80 as and when a client accesses the application.
- To automate this process, I modified a provisioning script so that upon starting up the virtual machine, there is a reverse proxy set up to ensure the application is redirected from port 3000 to port 80.

## Modification of provisioning script
```bash
sudo unlink /etc/nginx/sites-enabled/default
cd /etc/nginx/sites-available
sudo touch reverse-proxy.conf
sudo chmod 666 reverse-proxy.conf
echo "server{
  listen 80;
  location / {
      proxy_pass http://192.168.10.100:3000;
  }
}" >> reverse-proxy.conf
sudo ln -s /etc/nginx/sites-available/reverse-proxy.conf /etc/nginx/sites-enabled/reverse-proxy.conf
sudo service nginx restar
```
- The first line of code navigates to and removes the default file which establishes the default connection
- We then recreate the default file using touch - in my case I have named it reverse-proxy.conf
- The following line of code establish the writes of the file in our case we giving the file read and write privileges but not executable.
