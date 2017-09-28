##Itty bitty Etcd container

Etcd v3.2.7.

This image weighs in at 20.17 MB due to the inclusion of TLS support and etcdctl.  The `-data-dir` is a volume mounted to `/data`, and the default ports are bound to Etcd and exposed.

Since the image uses an `ENTRYPOINT` it accepts passthrough arguments to etcd.

```sh
docker run \
  -d \
  -p 2379:2379 \
  -p 2380:2380 \
  -v /data/backup/dir:/data \
  letniy/etcd:latest \
  -discovery=https://discovery.etcd.io/blahblahblahblah \
```

Orifinal github.com/colebrumley/docker-etcd.
