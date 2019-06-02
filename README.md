# Helm Char for `Redis commander`

**Redis commander** is management tool written in node.js for Redis.

To get more information about Redis commander go to [its web page](https://joeferner.github.io/redis-commander/)

## Installing the Chart

### From repository

Install the repository to have access to the chart

```
helm repo add pablobastidasv https://pablobastidasv.github.io/chart-repo/
```

Then, to install the chart with the release name `my-release`:

```console
$ helm install pablobastidasv/redis-commander --name my-release
```

# From chart code

To install the chart with the release name `my-release`:

```console
$ helm install . --name my-release
```

The command deploys **[redis-commander](https://joeferner.github.io/redis-commander/)** on the Kubernetes cluster with the default configuration. The [configuration](#configuration) section lists the parameters that can be configured during installation.

## Uninstalling the Chart

To uninstall/delete the `my-release` deployment:

```console
$ helm delete my-release --purge
```

The command removes all the Kubernetes components associated with the chart and deletes the release.

## Configuration

The following table lists the configurable parameters of the envoy chart and their default values.

Parameter | Description | Default
--- | --- | ---
`image.tag` | docker tag to define a specific version. | latest
`redis.service.name` | service name which provide access to redis cluster. | redis-master
`redis.service.port` | port to access the redis server. | `6379`
`redis.service.password.secret.name` | secret name which contains the redis' password.| `redis`
`redis.service.password.secret.key`| the secret's key where the password is stored. | `redis-password`
`ingress.enabled`| if `true` an ingress will be created. | false
`ingress.hosts`| a list of urls to access the service via ingress. | redis.localhost.xip.io

All other user-configurable settings, default values and some commentary about them can be found in [values.yaml](values.yaml).
