# app コンテナ起動
docker container run -v /Users/hako85/workspace/rals_channel/app/laravel:/home -p 55555:8000 -it rals_channel/laravel

# db コンテナ起動
docker container run --rm --name mydb -v /Users/hako85/workspace/rals_channel/db:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=password -p 33066:3306 -it mysql:5.7