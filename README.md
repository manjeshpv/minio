# Minio Quickstart Guide [![Gitter](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/minio/minio?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

Minio is an object storage server released under Apache License v2.0. It is compatible with Amazon S3 cloud storage service. It is best suited for storing unstructured data such as photos, videos, log files, backups and container / VM images. Size of an object can range from a few KBs to a maximum of 5TB.

##  1. Download

Minio server is light enough to be bundled with the application stack, similar to NodeJS, Redis and MySQL.

| Platform| Architecture | URL|
| ----------| -------- | ------|
|GNU/Linux|64-bit Intel|https://dl.minio.io/server/minio/release/linux-amd64/minio|
||32-bit Intel|https://dl.minio.io/server/minio/release/linux-386/minio|
||32-bit ARM|https://dl.minio.io/server/minio/release/linux-arm/minio|
|Apple OS X|64-bit Intel|https://dl.minio.io/server/minio/release/darwin-amd64/minio|
|Microsoft Windows|64-bit|https://dl.minio.io/server/minio/release/windows-amd64/minio.exe|
||32-bit|https://dl.minio.io/server/minio/release/windows-386/minio.exe|
|FreeBSD|64-bit|https://dl.minio.io/server/minio/release/freebsd-amd64/minio|

### Install from Source

Source installation is only intended for developers and advanced users. If you do not have a working Golang environment, please follow [How to install Golang](https://docs.minio.io/docs/how-to-install-golang).


```sh

$ go get -d github.com/minio/minio
$ cd $GOPATH/src/github.com/minio/minio
$ make

```

## 2. Run Minio Server


### GNU/Linux

 ```sh

$ chmod +x minio
$ ./minio --help
$ ./minio server ~/Photos

Endpoint:  http://10.0.0.10:9000  http://127.0.0.1:9000  http://172.17.0.1:9000
AccessKey: USWUXHGYZQYFYFFIT3RE
SecretKey: MOJRH0mkL1IPauahWITSVvyDrQbEEIwljvmxdq03
Region:    us-east-1

Browser Access:
   http://10.0.0.10:9000  http://127.0.0.1:9000  http://172.17.0.1:9000

Command-line Access: https://docs.minio.io/docs/minio-client-quick-start-guide
   $ mc config host add myminio http://10.0.0.10:9000 USWUXHGYZQYFYFFIT3RE MOJRH0mkL1IPauahWITSVvyDrQbEEIwljvmxdq03

Object API (Amazon S3 compatible):
   Go:         https://docs.minio.io/docs/golang-client-quickstart-guide
   Java:       https://docs.minio.io/docs/java-client-quickstart-guide
   Python:     https://docs.minio.io/docs/python-client-quickstart-guide
   JavaScript: https://docs.minio.io/docs/javascript-client-quickstart-guide

```

### OS X


 ```sh

$ chmod 755 minio
$ ./minio --help
$ ./minio server ~/Photos

Endpoint:  http://10.0.0.10:9000  http://127.0.0.1:9000  http://172.17.0.1:9000
AccessKey: USWUXHGYZQYFYFFIT3RE
SecretKey: MOJRH0mkL1IPauahWITSVvyDrQbEEIwljvmxdq03
Region:    us-east-1

Browser Access:
   http://10.0.0.10:9000  http://127.0.0.1:9000  http://172.17.0.1:9000

Command-line Access: https://docs.minio.io/docs/minio-client-quick-start-guide
   $ mc config host add myminio http://10.0.0.10:9000 USWUXHGYZQYFYFFIT3RE MOJRH0mkL1IPauahWITSVvyDrQbEEIwljvmxdq03

Object API (Amazon S3 compatible):
   Go:         https://docs.minio.io/docs/golang-client-quickstart-guide
   Java:       https://docs.minio.io/docs/java-client-quickstart-guide
   Python:     https://docs.minio.io/docs/python-client-quickstart-guide
   JavaScript: https://docs.minio.io/docs/javascript-client-quickstart-guide

```

### Microsoft Windows

```sh

C:\Users\Username\Downloads> minio.exe --help
C:\Users\Username\Downloads> minio.exe server D:\Photos

Endpoint:  http://10.0.0.10:9000  http://127.0.0.1:9000  http://172.17.0.1:9000
AccessKey: USWUXHGYZQYFYFFIT3RE
SecretKey: MOJRH0mkL1IPauahWITSVvyDrQbEEIwljvmxdq03
Region:    us-east-1

Browser Access:
   http://10.0.0.10:9000  http://127.0.0.1:9000  http://172.17.0.1:9000

Command-line Access: https://docs.minio.io/docs/minio-client-quick-start-guide
   $ mc.exe config host add myminio http://10.0.0.10:9000 USWUXHGYZQYFYFFIT3RE MOJRH0mkL1IPauahWITSVvyDrQbEEIwljvmxdq03

Object API (Amazon S3 compatible):
   Go:         https://docs.minio.io/docs/golang-client-quickstart-guide
   Java:       https://docs.minio.io/docs/java-client-quickstart-guide
   Python:     https://docs.minio.io/docs/python-client-quickstart-guide
   JavaScript: https://docs.minio.io/docs/javascript-client-quickstart-guide


```

### Docker Container

```sh

$ docker pull minio/minio
$ docker run -p 9000:9000 minio/minio

```

### FreeBSD

```sh

$ chmod 755 minio
$ ./minio --help
$ ./minio server ~/Photos

Endpoint:  http://10.0.0.10:9000  http://127.0.0.1:9000  http://172.17.0.1:9000
AccessKey: USWUXHGYZQYFYFFIT3RE
SecretKey: MOJRH0mkL1IPauahWITSVvyDrQbEEIwljvmxdq03
Region:    us-east-1

Browser Access:
   http://10.0.0.10:9000  http://127.0.0.1:9000  http://172.17.0.1:9000

Command-line Access: https://docs.minio.io/docs/minio-client-quick-start-guide
   $ mc config host add myminio http://10.0.0.10:9000 USWUXHGYZQYFYFFIT3RE MOJRH0mkL1IPauahWITSVvyDrQbEEIwljvmxdq03

Object API (Amazon S3 compatible):
   Go:         https://docs.minio.io/docs/golang-client-quickstart-guide
   Java:       https://docs.minio.io/docs/java-client-quickstart-guide
   Python:     https://docs.minio.io/docs/python-client-quickstart-guide
   JavaScript: https://docs.minio.io/docs/javascript-client-quickstart-guide


```

## 3. Test Minio Server using Minio Browser

Open a web browser and navigate to http://127.0.0.1:9000 to view your buckets on minio server.

![Screenshot](https://github.com/minio/minio/blob/master/docs/screenshots/minio-browser.jpg?raw=true)


## 4. Test Minio Server using `mc`


Install mc  from [here](https://docs.minio.io/docs/minio-client-quick-start-guide).  Use `mc ls` command to list all the buckets on your minio server.

```sh

$ mc ls myminio/
[2015-08-05 08:13:22 IST]     0B andoria/
[2015-08-05 06:14:26 IST]     0B deflector/
[2015-08-05 08:13:11 IST]     0B ferenginar/
[2016-03-08 14:56:35 IST]     0B jarjarbing/
[2016-01-20 16:07:41 IST]     0B my.minio.io/

```

For more examples please navigate to [Minio Client Complete Guide](https://docs.minio.io/docs/minio-client-complete-guide).


## 5. Explore Further

- [Minio Erasure Code QuickStart Guide](https://docs.minio.io/docs/minio-erasure-code-quickstart-guide)
- [Minio Docker Quickstart Guide](https://docs.minio.io/docs/minio-docker-container)
- [Use `mc` with Minio Server](https://docs.minio.io/docs/minio-client-quick-start-guide)
- [Use `aws-cli` with Minio Server](https://docs.minio.io/docs/how-to-use-aws-cli-with-minio)
- [Use `s3cmd` with Minio Server](https://docs.minio.io/docs/s3cmd-with-minio-server)
- [Use `minio-go` SDK with Minio Server](https://docs/golang-client-quickstart-guide)


## 6. Contribute to Minio Project
Please follow Minio [Contributor's Guide](https://github.com/minio/minio/blob/master/CONTRIBUTING.md)
