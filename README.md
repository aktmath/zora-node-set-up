# zora-node-set-up
Zora node set up guide

Follow the steps to set up your ZORA node

Execute the commands in order; if a window appears, press Yes + Enter.

````
sudo apt-get update && sudo apt-get update -y
````

````
sudo apt install curl build-essential git screen jq pkg-config libssl-dev libclang-dev ca-certificates gnupg lsb-release -y
````

````
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg
````

````
echo \
"deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
$(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
````


````
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose -y
````

````
git clone https://github.com/conduitxyz/node.git
````

````
cd node
````


````
./download-config.py zora-mainnet-0
````

````
export CONDUIT_NETWORK=zora-mainnet-0
````

# **Creating API Key**

Register on Alchemy

Go to Apps and click on Create New App

Generate API Key as shown in the screenshot

<img width="1000" alt="Untitled" src="https://github.com/aktmath/zora-node-set-up/assets/80599739/644b04c6-e2b5-44ec-980c-9a478c26cb16">

In the API Key, copy the HTTPS

Return to the node
Enter the following

````
cp .env.example .env
nano .env
````

````
screen -S log
````

````
docker compose up --build
````

Wait a couple of minutes; the logs will appear.


