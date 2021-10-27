# Synpse Ansible

Set of playbooks examples you can use with Synpse enabled devices. This helps you extend IoT fleet even further.

## Kiosk device

Create Kiosk device using Synpse ubuntu image.

```
# build an image
 sudo synpse build --image ubuntu-20.04.3-preinstalled-server-arm64+raspi.img --wifi-name SSID --wifi-password your_wifi_pass
```

``` 
ansible-playbook -i inventory/kiosk.sh playbooks/kiosk.yml
```

