### Nginx reverse proxy

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
