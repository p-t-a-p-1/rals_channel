## 各コンテナ起動コマンド  

-  app コンテナ起動  
    > docker container run --rm -v /Users/hako85/workspace/rals_channel/app/laravel:/home -p 55555:8000 -it rals_channel/laravel
  
- db コンテナ起動  
    > docker container run --rm --name mydb -v /Users/hako85/workspace/rals_channel/db:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=password -p 33066:3306 -it mysql:5.7
  

## docker-compose コマンド一覧  

- ymlファイル内に build: が定義されていれば image を build
    > docker-compose build
- ymlファイル内に image: が定義されていれば image を pull
    > docker-compose pull
- docker-compose build, docker-compose pull をした後に docker run (全部まとめてくれる)  
    > docker-compose up
- run したコンテナをまとめて終了
    > docker-compose stop
- コンテナをまとめて削除
    > docker-compose rm