# Checkpoint 7 - Mission Reflection: The Cloud Security Engineer

Completing Laboratory Activity 8 expanded my understanding of the importance of cloud security in operating and maintaining servers. I realized that successfully deploying an application is only one part of the process, as the server must also be protected from unauthorized access and potential network threats.

One of the key concepts I learned was how a host-based firewall adds another layer of protection to a server. Even when an organization's external security measures are compromised, a firewall running directly on the server can help control incoming connections according to predefined rules. This highlights the value of defense in depth, in which multiple security mechanisms work together to strengthen overall system protection.

I also gained a better understanding of why limiting exposed network ports is essential for reducing a server's attack surface. Each accessible service may introduce security risks if it contains vulnerabilities or has been improperly configured. By permitting only the necessary connections, such as SSH for remote administration and TCP port 8080 for the web application, administrators can minimize unnecessary network exposure.

Database protection was another important lesson from this activity. Exposing a database port, such as MySQL port 3306, directly to the public internet can increase the likelihood of unauthorized access, brute-force attempts, and data breaches. In an enterprise setting, database connections should be limited to trusted application servers or approved networks, supported by strong authentication and appropriate access permissions.

This laboratory also helped me recognize how easily a server can become vulnerable when firewall settings and other security measures are neglected. Working with UFW demonstrated the importance of implementing a Default Deny policy, explicitly permitting necessary traffic, and checking the active configuration to confirm that the intended security rules are in place.

Finally, completing eight cloud computing missions has helped me develop a more structured and professional GitHub portfolio. Recording commands, terminal screenshots, configuration details, and personal reflections has improved my ability to document technical activities and present my learning progress clearly.

Overall, this laboratory strengthened my practical knowledge of cloud security and taught me to view security as a continuous responsibility. Maintaining a secure cloud environment requires regular monitoring, careful configuration, and ongoing evaluation to help protect applications and system resources against potential threats.
