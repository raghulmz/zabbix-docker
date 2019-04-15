### How to build

```bash
$ cd zabbix-docker/agent/centos
$ docker build -t zabbix-docker-agent:<version> .
```

### How to RUN

```bash
$ docker run --name zabbix-docker-agent --volume /var/run/docker.sock:/var/run/docker.sock -d zabbix-docker-agent:<version>
$ docker exec -it zabbix-docker-agent bash
$ /usr/sbin/zabbix_agentd --foreground -c /etc/zabbix/zabbix_agentd.conf -t docker.discovery
docker.discovery                              [s|{"data":[{"{#FCONTAINERID}":"f093d826f871a638e1d848c55af41973c633a537f4889f1c5abb722c057f9ac4","{#SCONTAINERID}":"f093d826f871","{#SYSTEM.HOSTNAME}":"f093d826f871","{#HCONTAINERID}":"zabbix-docker-agent"}]}]

```
