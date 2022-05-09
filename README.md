## Requirements

1. sshpass

```bash
$ sudo apt-get install sshpass -y
```

2. curl

```bash
$ sudo apt-get install curl -y
```

3. Docker

```bash
$ sudo apt-get install ca-certificates gnupg lsb-release -y
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
$ sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin -y
```

4. Docker Compose

```bash
$ sudo apt-get install docker-compose-plugin -y
```

## Steps

```bash
$ sudo apt-get update
$ sudo apt-get upgrade -y
```
