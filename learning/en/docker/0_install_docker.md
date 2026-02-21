# Install docker with snap

```bash
sudo snap install docker
```

## Make service

```bash
sudo tee /etc/systemd/system/fix-docker-socket.service << 'EOF'
[Unit]
Description=Fix Docker socket permissions
After=snap.docker.dockerd.service

[Service]
Type=oneshot
ExecStart=/bin/bash -c 'chgrp docker /var/run/docker.sock && chmod 660 /var/run/docker.sock'
RemainAfterExit=yes

[Install]
WantedBy=multi-user.target
EOF
```

## Enable service

```bash
sudo systemctl enable fix-docker-socket.service
```
