![captagent](http://i.imgur.com/3kEIR.png)

# CAPTAGENT 6 Docker
http://sipcapture.org

Status: 

* [![Build Status](https://travis-ci.org/netaskd/captagent-docker.svg?branch=master)](https://travis-ci.org/netaskd/captagent-docker)

 
### Pull latest
```
docker pull bmerrills/captagent-docker
```

### Run latest using --net=host
```
docker run -tid --name captagent6 --net=host bmerrills/captagent-docker
```

### Local Build & Test
```
git clone https://github.com/qxip/captagent-docker; cd captagent-docker
docker build --tag="bmerrills/captagent-docker:local" ./
docker run --net=host -t -i qxip/captagent-docker:local
```

### Example docker-compose content
```
captagent:
  container_name: captagent
  image: qxip/captagent-docker
  restart: always
  net: host
  environment:
    - TERM=xterm
    - ETHERNET_DEV=any
    - CAPTURE_HOST=homer.domain.com
    - CAPTURE_PORT=9060
    - CAPTURE_PASSWORD=myHep
    - RTCP_ENABLE=true
    - LOG_LEVEL=3
    - CAPTURE_ID=1234
    - NAT_SUPPORT=true
```

