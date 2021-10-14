# Deploy 'IPSEC over L2TP VPN Server' to VM instance

Use docker image from https://hub.docker.com/r/hwdsl2/ipsec-vpn-server.

## Usage
### Enable APIs
Enable following service on your project. Access to link that easily can it.
* Cloud Build API
* Cloud Storage API
* Compute Engine API
* Service Networking API

🌐https://console.cloud.google.com/flows/enableapi?apiid=cloudbuild.googleapis.com%2Cstorage.googleapis.com%2Ccompute.googleapis.com%2Cservicenetworking.googleapis.com

### Enable service for Cloud Build Account
https://cloud.google.com/build/docs/securing-builds/configure-access-for-cloud-build-service-account
#### ![alt text](https://github.com/yaztak1227/deploy_vpn//blob/main/grant_service_account.png?raw=true)

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

### Access IP with vpn
Access to external ip. It has showed by terminal below the 'EXTERNAL_IP', If success of deployment.
#### ![alt text](https://github.com/yaztak1227/deploy_vpn//blob/main/readme_01.png?raw=true)
#### ![alt text](https://github.com/yaztak1227/deploy_vpn//blob/main/readme_02.png?raw=true)
