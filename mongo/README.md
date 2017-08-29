Start container console:
```sh
$ sudo docker exec -it mongodb bash 
```

Mongo access console:
```sh
>mongo
>db.col.insert({"a": 4})
```

Stop, start:
```sh
sudo docker stop mongodb
sudo docker start mongodb
```
