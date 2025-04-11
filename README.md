# FlexRIC Dev
xApp development environment using Near-RT FlexRIC from the Mosaic5G project

## Requirements

- make;
- Docker (20.10 or newer);

## Get Starting

### Get Repository
Clone the flexric-dev repository.

```shell
git clone https://github.com/muriloAvlis/flexric-dev
```

### Building RIC

To build the Near-RT RIC Docker image, run to following command:

```sh
make build-ric FLEXRIC_VERSION={flexric-branch}
```

### Building emulated CU and DU Images

To build the CU and DU Docker images, run to following command:

```sh
make build-cu-du
```

### Deployments Types

#### Near-RT FlexRIC deployment on Docker

```sh
docker container run -tid --name flexric --network host -e BIND_INTERFACE=[your-host-interface] --restart on-failure muriloavlis/flexric:latest
```

#### RIC deployment with emulated CU and DU on Docker
To deployment RIC, CU and DU with Docker Compose, run to following commands:

```sh
export NEAR_RIC_IP=<your-near-ric-ip>
make run-all
```

#### Near-RT FlexRIC deployment on Kubernetes

```sh
cd helm-chart/flexric
helm upgrade --install flexric -n flexric . --create-namespace -f values.yaml
```


#### xApp Deployment

TODO