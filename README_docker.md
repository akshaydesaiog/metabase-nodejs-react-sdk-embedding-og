cd server
docker build -t metabase-embedding-server .
docker run -d -p 9090:9090 --name metabase-embedding-server metabase-embedding-server

cd ../client
docker build -t metabase-embedding-client .
docker run -d -p 3100:3100 --name metabase-embedding-client metabase-embedding-client
