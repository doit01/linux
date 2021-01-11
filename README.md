netstat -aon|findstr "80"
docker-compose -f src/main/docker/redis.yml up -d

docker run -d --name myRedis -p 6379:6379 redis 
docker run -d --name redis6 -p 6379:6379 10.31.94.21:5000/redis  -v $PWD/data:/data --appendonly yes
