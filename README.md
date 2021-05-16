# testcontainers-python-and-conu

The original blogpost with the steps to setup Python testcontainers with ConU on Fedora.
https://fedoramagazine.org/test-containers-python-conu/

Was posted on Fedora Magazine https://fedoramagazine.org/


- To add $user to the docker group
```
sudo groupadd docker
sudo usermod -aG docker $USER
```
- Logout
- I restarted the docker service just in case. ```sudo service docker restart```
- See: https://docs.docker.com/engine/install/linux-postinstall/


References:
- Container Utilities: https://github.com/user-cont/conu
- Error docker (cgroups: cannot found cgroup mount destination: unknown): https://github.com/docker/for-linux/issues/219#issuecomment-375160449
- 
