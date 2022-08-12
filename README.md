# teamcity

Original idea is taken from https://gist.github.com/BenWhitehead/9422087

## Preparation steps

Update following lines in `teamcity-*.service` files

```
Environment="JAVA_HOME=..."
User
ExecStart
PIDFile
ExecStop
```

## Installation 

```Shell
sudo cp teamcity-agent.service /lib/systemd/system
sudo systemctl enable teamcity-agent

sudo cp teamcity-server.service /lib/systemd/system
sudo systemctl enable teamcity-server
```


To check a status
```Shell
sudo systemctl list-unit-files|grep -i teamcity
```

Output:
> teamcity-agent.service                        enabled   enabled


### Environment variable

copy java_home.sh file to /etc/profile.d folder if you need to start/stop services manually

```Shell
export JAVA_HOME=/usr/bin/java
```
