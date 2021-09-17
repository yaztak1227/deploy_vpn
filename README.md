# Deploy 'IPSEC over L2TP VPN Server' to VM instance

Use docker image from https://hub.docker.com/r/hwdsl2/ipsec-vpn-server.

## Usage
### Enable APIs
🌐https://console.cloud.google.com/flows/enableapi?apiid=cloudbuild.googleapis.com%2Cstorage.googleapis.com%2Ccompute.googleapis.com%2Cservicenetworking.googleapis.com

### Install gcloud commands
🌐https://cloud.google.com/sdk/gcloud

### Checkout & Checkout local
git@github.com:yaztak1227/deploy_vpn.git
OR
https://github.com/yaztak1227/deploy_vpn.git

### Edit vpn.env
Open vpn.env, And replace `<任意>` to your vpn settings.
```text
VPN_IPSEC_PSK=<任意>
VPN_USER=<任意>
VPN_PASSWORD=<任意>
```

### Put deploy on terminal
gcloud builds submit --config vpndeploy.yaml

### Access IP
Access to external ip. It has showed by terminal below the 'EXTERNAL_IP', If success of deployment.
