# Synpse Ansible

Set of `Ansible` playbooks you can use with Synpse enabled devices. 
This helps you extend IoT fleet even further.

## Kiosk device

Kiosk device will show webpage of your choice on the screen, connected to RPI or any other device.
We configure device from server build to UI using ansible, and manage web browser via Synpse application.

1. Create Pre-configured Synpse enabled IoT device. We use simple Ubuntu server image and will use ansible
playbook to configure the minimal GUI environment. This will create user, configure auto-login and pre-configure sleep and hibernation. 
```
# build an image
sudo synpse build --image ubuntu-20.04.3-preinstalled-server-arm64+raspi.img --wifi-name SSID --wifi-password your_wifi_pass
```

Install required packages for minimal GUI environment:
``` 
ansible-playbook -i inventory/kiosk.sh playbooks/kiosk.yml
```

2. Deploy Synpse application to the target device:
```
synpse deploy -f examples/kiosk.yaml
```