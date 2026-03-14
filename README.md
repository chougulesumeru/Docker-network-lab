# Create a networks first

docker network create my-bridge

docker network create frontend-net

# host network  -> we don't create it already exists

# none network -> we don't create it either

docker network create -d macvlan \ 
--subnet=192.168.1.0./24 \
--gateway=192.168.1.1 \ 
-o parent=eth0 \
my-maclvn

# overlay network (needs swarm or --atachable)

# for single host testing -> make it attachable

docker swarm init 

docker network create --driver overlay --attachable my-overlay 