#docker run mono c\#
```sh
docker pull mono
docker run -i -t mono bash
echo 'using System; public class HelloWorld { public static void Main(string[] args) { Console.WriteLine ("Hello Mono World");}}' >hello.cs
csc hello.cs
mono hello.exe
exit
```

#docker Desktop for macOS share files
Perferences->file sharing->add /Users/qiaobo/local/mei
```sh
docker run -it -v /Users/qiaobo/local/mei:/mei mono bash
```

#develep static web site using nginx
```sh
docker pull nginx
docker network create my-net
docker run -it --name mei-web --network my-net --publish 80:80 -v /Users/qiaobo/local/mei:/usr/share/nginx/html nginx bash
```
after that, you can
```sh
docker start mei-web
docker attach mei-web
nginx
```
