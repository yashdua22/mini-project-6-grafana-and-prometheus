# node-exporter Dockerfile
# (kept minimal; runtime needs host mounts/flags)
FROM prom/node-exporter:v1.8.2

# Default port
EXPOSE 9100

# Rootfs flag makes metrics (disk, fs) correct inside container
ENTRYPOINT ["/bin/node_exporter","--path.rootfs=/host"]