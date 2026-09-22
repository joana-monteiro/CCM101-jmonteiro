# Reflection — The Cloud-Native Engineer

This mission provided me with a valuable hands-on learning experience because I was able to work directly with **Docker containers** rather than only studying their concepts. At the beginning, I found it difficult to understand the differences between Virtual Machines and containers. However, after comparing their architecture, resource usage, and performance, I gained a clearer understanding of why containers are considered lightweight, efficient, and faster to deploy.

One of the most interesting parts of the activity was practicing Docker commands in the **KillerCoda Playground**. I used `docker --version` and `docker info` to examine the Docker environment. I then downloaded the Nginx image and created a container using `docker run`. Successfully receiving the Nginx Welcome Page through `curl` was satisfying because it demonstrated that I could deploy and test a functional web server using only a few commands.

I also encountered a challenge when trying to access the Nginx server through my browser. My first attempt was to use `localhost:8080`, but I learned that KillerCoda operates in a remote cloud environment. By using its **Traffic** feature, I was able to access the deployed web server. This experience helped me better understand port mapping and how cloud-based environments handle network connections.

Another important lesson was learning the **Docker container lifecycle**. Using commands such as `docker ps`, `docker stop`, `docker ps -a`, and `docker rm` allowed me to practice running, monitoring, stopping, verifying, and removing containers.

Overall, this mission increased my confidence in Docker and cloud environments. It also strengthened my troubleshooting and technical documentation skills. The activity showed me that learning cloud computing involves not only understanding concepts but also applying them through practical experience.
