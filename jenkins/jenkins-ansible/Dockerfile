FROM jenkins/jenkins

USER root
RUN apt-get update
RUN apt-get install curl && \
apt-get install wget && \
apt-get install python3-pip -y && \
curl -O https://bootstrap.pypa.io/get-pip.py && \ 
python3 get-pip.py && \
pip3 install ansible --upgrade
RUN wget https://packages.microsoft.com/config/debian/10/packages-microsoft-prod.deb && \
dpkg -i packages-microsoft-prod.deb && \
apt-get update && \
apt-get install powershell -y
RUN wget https://releases.hashicorp.com/terraform/1.0.11/terraform_1.0.11_linux_amd64.zip && \
unzip terraform_1.0.11_linux_amd64.zip && \
cp terraform /usr/local/bin/
USER jenkins
RUN pwsh -command Install-Module sqlserver -Force
RUN python3 -m pip install requests
