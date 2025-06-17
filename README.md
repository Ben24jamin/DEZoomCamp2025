# DEZoomCamp2025
how to stand up network create volume and stand up postgress and pgadmin on network using docker commands

##create a network for the services to run on (pgadmin and postgres)
docker network create pg-network
docker network disconnect name #stop networ
docker network rm name ##remove network image

##create a volume for postgress to write to 
docker volume create --name dtc_postgress_volume_local 


docker ps -a ## show all containers

docker stop my-container  # If the container is running
docker rm my-container #remove it


##stand up postgress

##network
docker network create pg-network

docker run -it \
  -e POSTGRES_USER="root" \
  -e POSTGRES_PASSWORD="root" \
  -e POSTGRES_DB="ny_taxi" \
  -v ny_taxi_data:/var/lib/postgresql/data \
  -p 5432:5432 \
  --network=pg-network \
  --name pg-database \
  postgres:13

##stand up pgadmin
  docker run -it \
  -e PGADMIN_DEFAULT_EMAIL="admin@admin.com" \
  -e PGADMIN_DEFAULT_PASSWORD="root" \
  -p 8080:80 \
  --network=pg-network \
  --name pgadmin \
    dpage/pgadmin4

wget https://github.com/DataTalksClub/nyc-tlc-data/releases/download/yellow/yellow_tripdata_2021-01.csv.gz 

/workspaces/DEZoomCamp2025/1.DockerIntro

