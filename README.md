Решение домашнего задания 4 «Оркестрация группой Docker контейнеров на примере Docker Compose»

Задача 1

https://hub.docker.com/repository/docker/tastysypchik/netology/general


Задача 2
```
sypchik@netology:~$ docker ps
CONTAINER ID   IMAGE            COMMAND       CREATED       STATUS       PORTS     NAMES
483c9808c414   ubuntu:22.04     "/bin/bash"   2 hours ago   Up 2 hours             ubuntu
ba46a3ec4d8d   centos:centos7   "/bin/bash"   2 hours ago   Up 2 hours             centos
sypchik@netology:~$ docker images
REPOSITORY   TAG       IMAGE ID       CREATED       SIZE
ubuntu       22.04     8a3cdc4d1ad3   11 days ago   77.9MB
centos       centos7   eeb6ee3f44bd   2 years ago   204MB
sypchik@netology:~$ docker build -t tastysypchik/netology:AU-custom-nginx-t2_1.0.0 .
[+] Building 8.5s (7/7) FINISHED                                                                                       docker:default
 => [internal] load build definition from Dockerfile                                                                             0.0s
 => => transferring dockerfile: 178B                                                                                             0.0s
 => [internal] load metadata for docker.io/library/nginx:stable                                                                  0.8s
 => [internal] load .dockerignore                                                                                                0.0s
 => => transferring context: 2B                                                                                                  0.0s
 => [internal] load build context                                                                                                0.0s
 => => transferring context: 165B                                                                                                0.0s
 => [1/2] FROM docker.io/library/nginx:stable@sha256:ac96a05e4b3dd2c57c9ca2637012f4fa17b11d5fdd2ce856c2f937bd843f0440            4.2s
 => => resolve docker.io/library/nginx:stable@sha256:ac96a05e4b3dd2c57c9ca2637012f4fa17b11d5fdd2ce856c2f937bd843f0440            0.0s
 => => sha256:d987469c32fecb3f839a4606671eb2bb308039a3a6b2d086341769da3931b9b6 2.29kB / 2.29kB                                   0.0s
 => => sha256:e7580268c63c006498d2140004ffe6f6fbf63ff75050a5dc46d6097f2004d577 7.28kB / 7.28kB                                   0.0s
 => => sha256:f11c1adaa26e078479ccdd45312ea3b88476441b91be0ec898a7e07bfd05badc 29.13MB / 29.13MB                                 0.7s
 => => sha256:d4e560a3091589fb95278a386add48626fbbe5bea3220576d6c4a838b4c65b24 41.83MB / 41.83MB                                 1.5s
 => => sha256:9ac6875eca605a2e2f0a434d6a2f461356f32dae78fb3d4b9be23c2d02d46ac3 627B / 627B                                       0.7s
 => => sha256:ac96a05e4b3dd2c57c9ca2637012f4fa17b11d5fdd2ce856c2f937bd843f0440 10.26kB / 10.26kB                                 0.0s
 => => extracting sha256:f11c1adaa26e078479ccdd45312ea3b88476441b91be0ec898a7e07bfd05badc                                        1.3s
 => => sha256:4ede7ada96f6d9d2bc1f6ef734c74b5c0bc60a2f64e8c8d368055152d6dfe689 394B / 394B                                       1.0s
 => => sha256:47927ca6802f832d4000bfcde5939632a8ff52d6e4149187f198834556ee16e9 956B / 956B                                       0.9s
 => => sha256:81bf9dd9cea603de3f08a37fb6f9156372709d0036479e6950b08b8b08dcf225 1.21kB / 1.21kB                                   1.6s
 => => sha256:434abd9d8a2b02240f4daaeca44eb14e422ff394d4e1628d6d3208faece25d7c 1.40kB / 1.40kB                                   1.6s
 => => extracting sha256:d4e560a3091589fb95278a386add48626fbbe5bea3220576d6c4a838b4c65b24                                        1.1s
 => => extracting sha256:9ac6875eca605a2e2f0a434d6a2f461356f32dae78fb3d4b9be23c2d02d46ac3                                        0.0s
 => => extracting sha256:47927ca6802f832d4000bfcde5939632a8ff52d6e4149187f198834556ee16e9                                        0.0s
 => => extracting sha256:4ede7ada96f6d9d2bc1f6ef734c74b5c0bc60a2f64e8c8d368055152d6dfe689                                        0.0s
 => => extracting sha256:81bf9dd9cea603de3f08a37fb6f9156372709d0036479e6950b08b8b08dcf225                                        0.0s
 => => extracting sha256:434abd9d8a2b02240f4daaeca44eb14e422ff394d4e1628d6d3208faece25d7c                                        0.0s
 => [2/2] COPY ./html/index.html /usr/share/nginx/html/                                                                          2.3s
 => exporting to image                                                                                                           0.5s
 => => exporting layers                                                                                                          0.3s
 => => writing image sha256:2c1a49677aadcf82a76de4142d3735ef1a10cdc2a3ffbafd2d885abb9e605d1d                                     0.0s
 => => naming to docker.io/tastysypchik/netology:AU-custom-nginx-t2_1.0.0                                                        0.1s
sypchik@netology:~$ docker run -d -p 8080:80 -it tastysypchik/netology:UAU-custom-nginx-t2_1.0.0
Unable to find image 'tastysypchik/netology:UAU-custom-nginx-t2_1.0.0' locally
docker: Error response from daemon: manifest for tastysypchik/netology:UAU-custom-nginx-t2_1.0.0 not found: manifest unknown: manifest unknown.
See 'docker run --help'.
sypchik@netology:~$ docker images
REPOSITORY              TAG                        IMAGE ID       CREATED          SIZE
tastysypchik/netology   AU-custom-nginx-t2_1.0.0   2c1a49677aad   56 seconds ago   188MB
ubuntu                  22.04                      8a3cdc4d1ad3   11 days ago      77.9MB
centos                  centos7                    eeb6ee3f44bd   2 years ago      204MB
sypchik@netology:~$ docker run -d -p 8080:80 -it tastysypchik/netology:AU-custom-nginx-t2_1.0.0
4cc975dd8273c93c95957d0c73b4bbd7b47657e133716cce804a4b3d7aeabf79
sypchik@netology:~$ curl http://127.0.0.1
curl: (7) Failed to connect to 127.0.0.1 port 80 after 0 ms: Connection refused
sypchik@netology:~$ curl http://127.0.0.1:8080
<html>
<head>
Hey, Netology
</head>
<body>
<h1>I will be DevOps Engineer!</h1>
</body>
</html>
sypchik@netology:~$ docker ps
CONTAINER ID   IMAGE                                            COMMAND                  CREATED          STATUS          PORTS                                   NAMES
4cc975dd8273   tastysypchik/netology:AU-custom-nginx-t2_1.0.0   "/docker-entrypoint.…"   48 seconds ago   Up 47 seconds   0.0.0.0:8080->80/tcp, :::8080->80/tcp   loving_driscoll
483c9808c414   ubuntu:22.04                                     "/bin/bash"              2 hours ago      Up 2 hours                                              ubuntu
ba46a3ec4d8d   centos:centos7                                   "/bin/bash"              2 hours ago      Up 2 hours                                              centos
sypchik@netology:~$ docker rename loving_driscoll custom-nginx-t2
sypchik@netology:~$ docker ps
CONTAINER ID   IMAGE                                            COMMAND                  CREATED              STATUS              PORTS                                   NAMES
4cc975dd8273   tastysypchik/netology:AU-custom-nginx-t2_1.0.0   "/docker-entrypoint.…"   About a minute ago   Up About a minute   0.0.0.0:8080->80/tcp, :::8080->80/tcp   custom-nginx-t2
483c9808c414   ubuntu:22.04                                     "/bin/bash"              2 hours ago          Up 2 hours                                                  ubuntu
ba46a3ec4d8d   centos:centos7                                   "/bin/bash"              2 hours ago          Up 2 hours                                                  centos
sypchik@netology:~$ date +"%d-%m-%Y %T.%N %Z" ; sleep 0.150 ; docker ps ; ss -tlpn | grep 127.0.0.1:8080  ; docker logs custom-nginx-t2 -n1 ; docker exec -it custom-nginx-t2 base64 /usr/share/nginx/html/index.html
09-07-2024 13:42:54.726248413 UTC
CONTAINER ID   IMAGE                                            COMMAND                  CREATED              STATUS              PORTS                                   NAMES
4cc975dd8273   tastysypchik/netology:AU-custom-nginx-t2_1.0.0   "/docker-entrypoint.…"   About a minute ago   Up About a minute   0.0.0.0:8080->80/tcp, :::8080->80/tcp   custom-nginx-t2
483c9808c414   ubuntu:22.04                                     "/bin/bash"              2 hours ago          Up 2 hours                                                  ubuntu
ba46a3ec4d8d   centos:centos7                                   "/bin/bash"              2 hours ago          Up 2 hours                                                  centos
172.17.0.1 - - [09/Jul/2024:13:42:00 +0000] "GET / HTTP/1.1" 200 95 "-" "curl/7.81.0" "-"
PGh0bWw+CjxoZWFkPgpIZXksIE5ldG9sb2d5CjwvaGVhZD4KPGJvZHk+CjxoMT5JIHdpbGwgYmUg
RGV2T3BzIEVuZ2luZWVyITwvaDE+CjwvYm9keT4KPC9odG1sPgo=
```

Задача 3
```
sypchik@netology:~$ docker ps
CONTAINER ID   IMAGE            COMMAND       CREATED             STATUS             PORTS     NAMES
483c9808c414   ubuntu:22.04     "/bin/bash"   About an hour ago   Up About an hour             ubuntu
ba46a3ec4d8d   centos:centos7   "/bin/bash"   About an hour ago   Up About an hour             centos
sypchik@netology:~$ docker images
REPOSITORY               TAG       IMAGE ID       CREATED        SIZE
ubuntu                   22.04     8a3cdc4d1ad3   11 days ago    77.9MB
portainer/portainer-ce   latest    a3f85c245ec3   2 months ago   293MB
registry                 2         6a3edb1d5eb6   9 months ago   25.4MB
centos                   centos7   eeb6ee3f44bd   2 years ago    204MB
sypchik@netology:~$ docker build -t tastysypchik/netology:UAU-custom-nginx-t2 .
[+] Building 2.0s (8/8) FINISHED                                                                                       docker:default
 => [internal] load build definition from Dockerfile                                                                             0.2s
 => => transferring dockerfile: 178B                                                                                             0.1s
 => [internal] load metadata for docker.io/library/nginx:stable                                                                  1.1s
 => [auth] library/nginx:pull token for registry-1.docker.io                                                                     0.0s
 => [internal] load .dockerignore                                                                                                0.1s
 => => transferring context: 2B                                                                                                  0.0s
 => [internal] load build context                                                                                                0.1s
 => => transferring context: 60B                                                                                                 0.1s
 => [1/2] FROM docker.io/library/nginx:stable@sha256:ac96a05e4b3dd2c57c9ca2637012f4fa17b11d5fdd2ce856c2f937bd843f0440            0.0s
 => CACHED [2/2] COPY ./html/index.html /usr/share/nginx/html/                                                                   0.0s
 => exporting to image                                                                                                           0.0s
 => => exporting layers                                                                                                          0.0s
 => => writing image sha256:e9a9ed18329c674d65ce70fc89641db5ce4c0ad977a3c485a8e3393faeb3e32d                                     0.0s
 => => naming to docker.io/tastysypchik/netology:UAU-custom-nginx-t2                                                             0.0s
sypchik@netology:~$ docker images
REPOSITORY               TAG                   IMAGE ID       CREATED        SIZE
tastysypchik/netology    UAU-custom-nginx-t2   e9a9ed18329c   2 hours ago    188MB
ubuntu                   22.04                 8a3cdc4d1ad3   11 days ago    77.9MB
portainer/portainer-ce   latest                a3f85c245ec3   2 months ago   293MB
registry                 2                     6a3edb1d5eb6   9 months ago   25.4MB
centos                   centos7               eeb6ee3f44bd   2 years ago    204MB
sypchik@netology:~$ docker run -d --name nginx  -p 8080:80 -it UAU-custom-nginx-t2
docker: invalid reference format: repository name (library/UAU-custom-nginx-t2) must be lowercase.
See 'docker run --help'.
sypchik@netology:~$ docker run -d --name nginx  -p 8080:80 -it tastysypchik/netology:AU-custom-nginx-t2
Unable to find image 'tastysypchik/netology:AU-custom-nginx-t2' locally
AU-custom-nginx-t2: Pulling from tastysypchik/netology
Digest: sha256:dcdd63044146661ba31a615cde54a4c4798eac9cedfff65a8dd245b4d91c2476
Status: Downloaded newer image for tastysypchik/netology:AU-custom-nginx-t2
1ca525a731daf2b7dcc59decfef737294ca4e5f721d46a6498025bef581bf59f
sypchik@netology:~$ docker ps
CONTAINER ID   IMAGE                                      COMMAND                  CREATED             STATUS             PORTS                                   NAMES
1ca525a731da   tastysypchik/netology:AU-custom-nginx-t2   "/docker-entrypoint.…"   4 seconds ago       Up 3 seconds       0.0.0.0:8080->80/tcp, :::8080->80/tcp   nginx
483c9808c414   ubuntu:22.04                               "/bin/bash"              About an hour ago   Up About an hour                                           ubuntu
ba46a3ec4d8d   centos:centos7                             "/bin/bash"              About an hour ago   Up About an hour                                           centos
sypchik@netology:~$ curl http://10.128.0.6:8080
<html>
<head>
Hey, Netology
</head>
<body>
<h1>I will be DevOps Engineer!</h1>
</body>
</html>
sypchik@netology:~$ curl http://10.128.0.6:80
curl: (7) Failed to connect to 10.128.0.6 port 80 after 0 ms: Connection refused
sypchik@netology:~$ docker exec -it nginx /bin/bash
root@1ca525a731da:/# apt update > /dev/null 2>&1
root@1ca525a731da:/# apt install nano net-tools -y > /dev/null 2>&1
root@1ca525a731da:/# sed -i "s|80|81|g" /etc/nginx/conf.d/default.conf
root@1ca525a731da:/# cat /etc/nginx/conf.d/default.conf | grep 81
    listen       81;
    listen  [::]:81;
    # proxy the PHP scripts to Apache listening on 127.0.0.1:81
root@1ca525a731da:/# nginx -s reload
2024/07/09 13:11:25 [notice] 205#205: signal process started
root@1ca525a731da:/# netstat -ntulp | grep 81
tcp        0      0 0.0.0.0:81              0.0.0.0:*               LISTEN      1/nginx: master pro
tcp6       0      0 :::81                   :::*                    LISTEN      1/nginx: master pro
root@1ca525a731da:/# exit
exit
sypchik@netology:~$ curl http://10.128.0.6:8080
curl: (7) Failed to connect to 10.128.0.6 port 8080 after 0 ms: Connection refused
sypchik@netology:~$ docker stop nginx
sypchik@netology:~$ docker commit nginx nginx-81
sha256:a67e964df1947aa3fe50fc7c7a8d8f5d5f54ae2793c0df2e0e1b935fae86520e
sypchik@netology:~$ docker images
REPOSITORY               TAG                   IMAGE ID       CREATED         SIZE
nginx-81                 latest                a67e964df194   6 seconds ago   210MB
tastysypchik/netology    AU-custom-nginx-t2    e9a9ed18329c   3 hours ago     188MB
tastysypchik/netology    UAU-custom-nginx-t2   e9a9ed18329c   3 hours ago     188MB
ubuntu                   22.04                 8a3cdc4d1ad3   11 days ago     77.9MB
portainer/portainer-ce   latest                a3f85c245ec3   2 months ago    293MB
registry                 2                     6a3edb1d5eb6   9 months ago    25.4MB
centos                   centos7               eeb6ee3f44bd   2 years ago     204MB
sypchik@netology:~$ docker ps
CONTAINER ID   IMAGE            COMMAND       CREATED       STATUS       PORTS     NAMES
483c9808c414   ubuntu:22.04     "/bin/bash"   2 hours ago   Up 2 hours             ubuntu
ba46a3ec4d8d   centos:centos7   "/bin/bash"   2 hours ago   Up 2 hours             centos
sypchik@netology:~$ docker run -d --name nginx-81  -p 8080:81 -it nginx-81
ba565dd69c21701fd2055d8560a1fe6d3a2e67ec2aa0bc28d5d3dac30125ba90
sypchik@netology:~$ curl http://10.128.0.6:8080
<html>
<head>
Hey, Netology
</head>
<body>
<h1>I will be DevOps Engineer!</h1>
</body>
</html>
sypchik@netology:~$ docker tag nginx-81:latest tastysypchik/netology:AU-custom-nginx-t3
sypchik@netology:~$ docker images
REPOSITORY               TAG                   IMAGE ID       CREATED              SIZE
nginx-81                 latest                a67e964df194   About a minute ago   210MB
tastysypchik/netology    AU-custom-nginx-t2    a67e964df194   About a minute ago   210MB
tastysypchik/netology    AU-custom-nginx-t3    a67e964df194   About a minute ago   210MB
tastysypchik/netology    UAU-custom-nginx-t2   e9a9ed18329c   3 hours ago          188MB
ubuntu                   22.04                 8a3cdc4d1ad3   11 days ago          77.9MB
portainer/portainer-ce   latest                a3f85c245ec3   2 months ago         293MB
registry                 2                     6a3edb1d5eb6   9 months ago         25.4MB
centos                   centos7               eeb6ee3f44bd   2 years ago          204MB
sypchik@netology:~$ docker tag nginx-81:latest tastysypchik/netology:UAU-custom-nginx-t2
sypchik@netology:~$ docker ps
CONTAINER ID   IMAGE            COMMAND                  CREATED              STATUS              PORTS                                           NAMES
ba565dd69c21   nginx-81         "/docker-entrypoint.…"   About a minute ago   Up About a minute   80/tcp, 0.0.0.0:8080->81/tcp, :::8080->81/tcp   nginx-81
483c9808c414   ubuntu:22.04     "/bin/bash"              2 hours ago          Up 2 hours                                                          ubuntu
ba46a3ec4d8d   centos:centos7   "/bin/bash"              2 hours ago          Up 2 hours                                                          centos
sypchik@netology:~$ docker images
REPOSITORY               TAG                   IMAGE ID       CREATED         SIZE
nginx-81                 latest                a67e964df194   2 minutes ago   210MB
tastysypchik/netology    AU-custom-nginx-t2    a67e964df194   2 minutes ago   210MB
tastysypchik/netology    AU-custom-nginx-t3    a67e964df194   2 minutes ago   210MB
tastysypchik/netology    UAU-custom-nginx-t2   a67e964df194   2 minutes ago   210MB
tastysypchik/netology    <none>                e9a9ed18329c   3 hours ago     188MB
ubuntu                   22.04                 8a3cdc4d1ad3   11 days ago     77.9MB
portainer/portainer-ce   latest                a3f85c245ec3   2 months ago    293MB
registry                 2                     6a3edb1d5eb6   9 months ago    25.4MB
centos                   centos7               eeb6ee3f44bd   2 years ago     204MB
sypchik@netology:~$ docker stop nginx-81
nginx-81
sypchik@netology:~$ docker run -d -p 8080:81 -it tastysypchik/netology:UAU-custom-nginx-t2
8b597c7714589c8790603f4531a836187c035e9560c90ad93042da072eadda0a
sypchik@netology:~$ docker ps
CONTAINER ID   IMAGE                                       COMMAND                  CREATED         STATUS         PORTS                                           NAMES
8b597c771458   tastysypchik/netology:UAU-custom-nginx-t2   "/docker-entrypoint.…"   3 seconds ago   Up 3 seconds   80/tcp, 0.0.0.0:8080->81/tcp, :::8080->81/tcp   amazing_sinoussi
483c9808c414   ubuntu:22.04                                "/bin/bash"              2 hours ago     Up 2 hours                                                     ubuntu
ba46a3ec4d8d   centos:centos7                              "/bin/bash"              2 hours ago     Up 2 hours                                                     centos
sypchik@netology:~$ curl http://10.128.0.6:8080
<html>
<head>
Hey, Netology
</head>
<body>
<h1>I will be DevOps Engineer!</h1>
</body>
</html>
```
Задача 4
![Screenshot 2024-07-09 144332](https://github.com/Borschik27/netologyHW/assets/121562626/952b5676-3d90-4430-b8e9-e56c929f4da1)

Задача 5
![Screenshot 2024-07-09 150749](https://github.com/Borschik27/netologyHW/assets/121562626/ec576f7c-512e-400a-8d05-f6d0b393062c)
![Screenshot 2024-07-09 150833](https://github.com/Borschik27/netologyHW/assets/121562626/60f9cd47-cb12-43f5-ae8c-b7163572045b)
![Screenshot 2024-07-09 150853](https://github.com/Borschik27/netologyHW/assets/121562626/252baa78-c168-49b2-b54c-f3b41c35c70e)
![Screenshot 2024-07-09 150839](https://github.com/Borschik27/netologyHW/assets/121562626/c6c80f24-16b0-44d6-b194-bca8f791014f)
![Screenshot 2024-07-09 150945](https://github.com/Borschik27/netologyHW/assets/121562626/44bc79cb-9767-431d-9e99-a956bb8306a5)
![Screenshot 2024-07-09 151254](https://github.com/Borschik27/netologyHW/assets/121562626/8a1eee5a-11e5-4238-9be6-f9073800737e)
