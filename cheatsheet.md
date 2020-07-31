### Linux commands cheat sheet
### Session Management

- ``` top ``` --> Show real time processes
- ``` killall name ``` --> Kill all the processes with that name
- ``` uname ``` --> Displays name of the Operating System
- ``` pwd ``` --> Shows Current File Location
- ``` sudo command ``` --> Runs the Command as Admin
- ``` sudo su ``` --> Changes To Root User
- ``` exit ``` --> Return Back To Normal User

---
### File Operations


- ``` touch filename ``` --> Create a file
- ``` nano filename ``` --> Enter a file
- ``` rm filename ``` --> Remove a file
- ``` file filename ``` --> Get type of file
- ``` head filename ``` Shows first 10 lines of file
- ``` tail filename ``` --> Shows last 10 lines of file

---

### File Permissions

- ``` chmod +x filename ``` --> Give executable permission to a file

---
### Directory Operations

- ``` mkdir directory ``` --> Create A Directory
- ``` cd directory ``` --> Entry Inside Of A Directory
- ``` cd .. ``` --> Exit A Directory
- ``` cd / ``` --> Return to the root directory
- ``` ls ``` --> Check Contents Of A Directory
- ``` ls -a ``` --> Check All Files in A directory (include those Hidden)

---
### Bash Variables

- ``` env ``` --> Shows all the Environment Variables
- ``` name ="Andrew" ```
- ``` echo $name ``` --> Displaying the value of the variable
- ``` export name ="Andrew" ``` --> Making name an Environment Variable

---
### Bash Script Commands

- ``` > command ```  --> Redirects Output to a File
- ``` >> command ``` --> Redirects Output to a File and Appends Output To End Of File
e.g..

```
echo "server{listen 80;
  listen 80;
  location / {
      proxy_pass http://192.168.10.100.3000;
  }
}" >> reverse-proxy.conf
```

The command in the echo will be added into the file named 'reverse-proxy.config'
