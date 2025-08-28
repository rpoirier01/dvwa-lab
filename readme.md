# DVWA Lab

This is a hands-on lab I completed in which I pentested a containerized version of the Damn Vulnerable Web App (DVWA). In addition to the pentesting, I created Prometheus alerts for visibility
and I built a basic Grafana dashboard to build familiarity with the technology. I also set up a simple CI/CD pipeline to perform a vulnerability scan of the DVWA Docker image, and then pull it.
For more detailed information, please see **WRITEUP.md**.
## Disclaimer
Some tools in this lab have the potential to be used maliciously. The OWASP ZAP vulnerability scanner was run exclusively on a web application locally hosted on my machine. I did not scan any 3rd party systems, and I do not condone any unethical use of OWASP ZAP or any other pentesting tool. While I may discuss different types of attacks and their methodology, I am only supplying information readily available on cybersecurity sites like OWASP. I do not intend to encourage any type of illegal or unethical cyberattack, this project was purely for personal learning. 

## Note On AI Use
Some of the results in this lab were the result of AI assisted research and troubleshooting along with AI generated code. I tried to do as much of this lab hands-on as possible, but I still 
relied on AI when I ran into issues. For full details of AI usage, see the **WRITEUP.md** file, as I tried to note them specifically there. 

## Tools Used
- Damn Vulnerable Web App (DVWA) - A web app which has intentional security vulnerabilities. It features different levels of security to learn pentesting. 
- OWASP ZAP - An open source vulnerability scanner and pentesting tool. I chose it for its beginner friendly nature and well-documented functionality. 
- Docker/Docker Desktop - Used to deploy and manage containers.
- Prometheus/Grafana - For monitoring containerized applications.
- GitHub Actions - To simulate a CI/CD pipeline 
- Wireshark - Used to capture packets at certain points during pentesting.
- Linux Mint - My host operating system of choice for this project.

## Brief Summary of Results
I deployed a containerized version of DVWA and other relevant tools using Docker and Docker Desktop.
I was able to conduct a basic pentest of several common web vulnerabilities including SQL injection, command inject and a brute force attack. For the brute force attack, I used the OWASP ZAP fuzz tool, which allowed me to simulate testing with about twenty passwords. Afterwards, I monitored the instance with Prometheus blackbox and created alerts for different activity such as repeated HTTP errors, blackbox probes failing consistently and the probe duration being abnormally long. I attempted to create a Grafana dashboard with the blackbox metrics, but I could not access them through Prometheus. Instead, I made a Grafana dashboard monitoring basic metrics about Prometheus like HTTP duration and CPU seconds used in the last 10 minutes. I then used GitHub Actions to make a CI/CD pipeline which performed a vulnerability scan of the DVWA container before pulling it. 
