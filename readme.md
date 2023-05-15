### Kafka Cluster - Docker Compose
This setup provides a Kafka cluster with three Kafka nodes, along with UIs for Kafka management using kafka UI and kouncil.

#### How to Run
To start the Kafka cluster, run the following command:

```sh
docker-compose up -d
```
Before connecting to the cluster from outside Docker (e.g., from your PC), you need to configure the hosts file on your Docker host. Follow the instructions below based on your operating system:

#### Linux Example:
Open a terminal and run the following command:
```sh
sudo nano /etc/hosts
```
Add the following lines to the file:
```sh
127.0.0.1 kafka01
127.0.0.1 kafka02
127.0.0.1 kafka03

```
Save the file and exit.
Done!

#### Connection String (Public)
Use the following connection string to connect to the Kafka cluster from outside Docker:

```sh
kafka01:29192,kafka02:29292,kafka03:29392
```
This connection string includes the hostnames and port numbers for the Kafka nodes.

#### Kafka UI
You can access the Kafka UI using the following URL:

* Kafka UI
This UI provides a graphical interface for managing Kafka topics, producers, and consumers.

#### Kouncil UI
You can access the Kouncil UI using the following URL:

* Kouncil UI
Kouncil is another UI for Kafka management, offering additional features and functionality.

Feel free to explore and utilize these UIs for managing your Kafka cluster.