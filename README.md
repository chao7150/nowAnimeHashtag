This software is released under the MIT License, see LICENSE.txt.

# Get Started

`$ git clone https://github.com/yukihirai0505/dog_api`

## Edit application.conf

Edit `src/main/resources/application.conf`

```application.conf
mysql = {
  dataSourceClass="com.mysql.cj.jdbc.MysqlDataSource"
  properties {
    user="[ユーザー名]"
    password="[パスワード]"
    databaseName="[作成したDB名]"
    serverName="localhost"
    portNumber="3306"
  }
  numThreads=10
}
```

## Run App

```
$ docker-compose up -d --build # <= DockerでDBを用意する場合
$ sbt run
```


## curlでテスト

- list dogs

`$ curl --request GET 'localhost:8080/dogs'`

- create a new dog

`$ curl -H "Content-Type: application/json" --request POST 'localhost:8080/dogs'  -d '{"name":"NEW DOG"}'`

- show the dog

`$ curl --request GET 'localhost:8080/dogs/1'`

- update the dog

`$ curl -H "Content-Type: application/json" --request PUT 'localhost:8080/dogs/1'  -d '{"name":"Updated DOG"}'`

- delete the dog

`$ curl --request DELETE 'localhost:8080/dogs/1'`
