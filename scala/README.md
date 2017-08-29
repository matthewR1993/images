Assemble jar before building container:
Dev:
```sh
$ sbt assembly
```

Build it:
```sh
$ sudo docker build -t jar-app .
```

Run it:
```sh
$ sudo docker run -it --name jar-app -p 8080:8080 -m=3GB -e JAVA_OPTS='-Xms1024M -Xmx2048M' jar-app:lates
```

