

## How to build this image


```shell
cd libs

# Download the rpm from the following location and put it inside libs folder
# https://download.oracle.com/otn/linux/instantclient/11204/oracle-instantclient11.2-basic-11.2.0.4.0-1.x86_64.rpm
cd ..
docker build -t ankitrakuten/cos-go-oracle:latest .
docker push ankitrakuten/cos-go-oracle:latest
```
