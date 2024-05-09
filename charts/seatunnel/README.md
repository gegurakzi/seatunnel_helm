## SeaTunnel on K8s Helm Chart

```
helm install seatunnel seatunnel
```

example job
```

```
you can ckeck whether seatunnel cluster has successfully deployed by these commands.



```
kubectl exec -it  seatunnel-0  -- /opt/seatunnel/bin/seatunnel.sh --config /data/seatunnel.streaming.conf
kubectl exec -it  seatunnel-0  -- tail -f /opt/seatunnel/logs/seatunnel-engine-server.log | grep ConsoleSinkWriter
```


