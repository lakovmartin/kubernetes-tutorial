## docker build -t getting-started .

## docker run -dp 3000:3000 getting-started

## http://localhost:3000. 


## <p className="text-center">No items yet! Add one above!</p>
##  <p className="text-center">You have no todo items yet! Add one above!</p>


docker ps
docker stop
docker rm

docker run -dp 3000:3000 getting-started



 docker volume create todo-db

docker run -dp 3000:3000 -v todo-db:/etc/todos getting-started

docker volume inspect