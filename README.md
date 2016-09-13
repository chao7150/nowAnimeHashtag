# Get Started

`git clone `

##Edit application.conf

Edit `src/main/resources/application.conf`

```application.conf
mysql = {
  dataSourceClass="com.mysql.jdbc.jdbc2.optional.MysqlDataSource"
  properties {
    user="[ユーザー名]"
    password="[パスワード]"
    databaseName="[作成したDB名]"
    serverName="localhost"
  }
  numThreads=10
}
```

## Run App

`sbt run`


## curlでテスト

- list dogs

`curl --request GET 'localhost:8080/dogs/1'`

- create a new dog

`curl -H "Content-Type: application/json" --request POST 'localhost:8080/dogs'  -d '{"name":"NEW DOG"}'`

- show the dog

`curl --request GET 'localhost:8080/dogs/1'`

- update the dog

`curl -H "Content-Type: application/json" --request PUT 'localhost:8080/dogs/1'  -d '{"name":"Updated DOG"}'`

- delete the dog

`curl --request DELETE 'localhost:8080/dogs/1'`