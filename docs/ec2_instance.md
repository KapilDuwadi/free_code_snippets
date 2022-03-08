
### Connecting to EC2 instance via SSH

```
ssh  -i <pem_file> ec2-user@<public-ip-address>
```

### Copying file/folders from local computer to EC2 instance 

```
scp -i <pem-file> <source> ec2-user@<public-ip-address>:~/home/<destination>
```


### Creating screen to perform long running simulation
```
screen -S <screen-name>

Execute long running code
Click Ctrl + A + D to exit from screen

screen -r <screen-name> (will recover the scree)
screen -X -S <screen-name> quit (will delete the detached screen)
```

### Connecting to Mongo Shell from EC2 instance
```
mongo "mongodb+srv://<cluster-address>/<primary-database>" --username <my-user>
```

### Importing data to Mongo Collection from file using Mongo Shell
```
mongoimport mongodb+srv://<user>:<password>@<mongo-host> --db <primary-address> --collection <collection-name> --file <json-file-path> --jsonArray

sudo yum install mongodb-org-tools (if mongoimport is not found)
```




