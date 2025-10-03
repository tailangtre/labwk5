# wk5-Packer-intro-lab-start

Web Front Packer Lab

This project demonstrates creating a Debian 13 AMI with Nginx using HashiCorp Packer. The AMI serves a custom HTML page included in this repository.

Project Files

- files/index.html – HTML page to serve  
- files/nginx.conf – Nginx configuration file  
- scripts/install-nginx – Script to install Nginx  
- scripts/setup-nginx – Script to configure and enable Nginx  
- web-front.pkr.hcl – Packer template to build the AMI  

Building the AMI

1. Clone the repository:

git clone <repo url>
cd wk5-packer-intro-lab-start

2. Validate the Packer template:

packer validate web-front.pkr.hcl

3. Build the AMI:

packer build -force web-front.pkr.hcl

The -force option ensures Packer ignores cached artifacts from previous builds.

Launching an EC2 Instance

1. Go to the AWS Management Console → EC2 → AMIs.  
2. Find the newly created AMI (web-nginx-aws).  
3. Launch a new instance using this AMI (t3.micro recommended).  
4. Ensure the security group allows HTTP (port 80).  
5. Once running, note the instance's public IP.

Testing the Web Page

Open a browser and visit:

http://<public-ip>

You should see the index.html page served by Nginx.

Screenshot

[Web page served by Nginx] (screenshot.png)


This confirms that the AMI successfully installs Nginx, sets proper permissions, and serves the included HTML page.

Replace <your-repo-link> with your Git repository URL, <public-ip> with the instance's public IP, and screenshot.png with your actual screenshot file.

