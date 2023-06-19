# DOMjudge deployments

[DOMjudge](https://www.domjudge.org/)

## Dependencies
For debian:
> In /etc/default/grub, add 'cgroup_enable=memory swapaccount=1 systemd.unified_cgroup_hierarchy=0' to GRUB_CMDLINE_LINUX_DEFAULT.

```bash
update-grub
reboot
```

## Kubernetes

```bash
cd kubernetes
kubectl apply -f .
```

## Docker compose

```bash
cd docker
docker-compose up -d
```

## Other

For generated admin password check `domserver` container logs.  
Change `judgehost` user password in web ui to the one you set in env - `JUDGEDAEMON_PASSWORD`.