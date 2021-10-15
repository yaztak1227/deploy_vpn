# Deploy 'IPSEC over L2TP VPN Server' to VM instance

Use docker image from https://hub.docker.com/r/hwdsl2/ipsec-vpn-server.
Easily deploy and run 'IPSEC over L2TP VPN Server' on your projects by Google Cloud Build.

## Usage
### Enable APIs
Enable following service on your project. You can access to link that easily do it.
* Cloud Build API
* Cloud Storage API
* Compute Engine API
* Service Networking API

🌐https://console.cloud.google.com/flows/enableapi?apiid=cloudbuild.googleapis.com%2Cstorage.googleapis.com%2Ccompute.googleapis.com%2Cservicenetworking.googleapis.com

### Install gcloud commands
🌐https://cloud.google.com/sdk/gcloud

### Clone & Checkout local
git@github.com:yaztak1227/deploy_vpn.git

OR

https://github.com/yaztak1227/deploy_vpn.git

### Edit vpn.env
Open vpn.env file. Please replace `<任意>` to your vpn settings and saving file.
```text
VPN_IPSEC_PSK=<任意>
VPN_USER=<任意>
VPN_PASSWORD=<任意>
```

### Put deploy command on terminal
Put the command following text on terminal.

`gcloud builds submit --config vpndeploy.yaml`

### Put firewall edit command on terminal
Put the command following text on terminal.

`gcloud compute --project=nice-argon-329000 firewall-rules create vpn --direction=INGRESS --priority=1000 --network=default --action=ALLOW --rules=udp:500,udp:4500 --source-ranges=0.0.0.0/0 --target-tags=vpn`

### Access IP with vpn
Access to external ip. It has showed by terminal below the 'EXTERNAL_IP', If success of deployment.
#### ![alt text](https://github.com/yaztak1227/deploy_vpn//blob/main/readme_01.png?raw=true)
#### ![alt text](https://github.com/yaztak1227/deploy_vpn//blob/main/readme_02.png?raw=true)
