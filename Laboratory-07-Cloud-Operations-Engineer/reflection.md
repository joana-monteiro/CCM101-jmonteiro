# Mission Reflection

Participating in this laboratory as a Cloud Operations Engineer helped me realize that maintaining a system is just as essential as developing and deploying it. One of the key lessons I gained was the importance of monitoring the host machine's resources, even when the containers seem to be operating normally. Similar to how a building relies on a solid foundation, containers depend on the host system's CPU, RAM, and disk storage. When these resources become limited, applications inside containers may encounter errors or crashes, even if they initially appear to be functioning correctly.

## Troubleshooting Through Logs

When investigating technical issues, such as users being unable to log in, the `docker logs` command serves as a useful troubleshooting tool. It allows me to review the events recorded by a container and identify potential causes, including database connectivity issues and authentication errors. Through this activity, I also learned to distinguish logs from metrics. Logs describe what happened within an application, such as a `404 Not Found` response, while metrics indicate how the system is performing through measurements like CPU utilization and memory consumption. Both are important for identifying problems and maintaining application reliability.

## Monitoring and Automation

I also realized that manually monitoring thousands of containers would be challenging for large organizations. Monitoring tools such as Prometheus can automatically collect system metrics, while Grafana displays the collected data through visual dashboards. When combined with automated alerts, these tools enable cloud engineers to identify unusual system behavior and respond to potential issues more quickly and efficiently.

## Developing My Technical Skills

This laboratory also improved my confidence in working with Linux environments, troubleshooting technical problems, and monitoring Docker containers. Commands such as `top`, `df -h`, and `docker stats` have become more familiar to me. Tasks that initially seemed complicated are now practical methods I can use to examine system performance, identify resource limitations, and understand how applications use available resources.

Overall, this experience taught me that effective cloud operations involve more than deploying applications. They also require continuous resource monitoring, log analysis, problem identification, and the maintenance of reliable services. I have learned to evaluate application health using actual system measurements and recorded events rather than relying solely on assumptions. These skills will help me better understand how to maintain stable and efficient cloud environments in the future.
