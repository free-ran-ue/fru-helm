# Helm Chart for free-ran-ue

## Env Setting

Please refer to [free5GC's official user guide](https://free5gc.org/guide/7-free5gc-helm/) to install free5GC's microk8s environment.

## clone and Run

```bash
git clone https://github.com/free-ran-ue/helm
helm install -n free5gc fru ./free-ran-ue
```

It is optinal to install free-ran-ue in `-n free5gc`.

## Start gNB & UE

### gNB

gNB will start automatically after the pod starting.

### UE

- Get into the pod

    ```bash
    kubectl exec -it -n free5gc fru-freeranue-ue-xxxxxxxxxx-xxxxx -- sh
    ```

- Run UE

    ```bash
    ./free-ran-ue ue -c config/ue.yaml
    ```

- Ping Test

    Open another terminal and get into the pod

    ```bash
    ping -I uetun0 10.100.100.13
    ```

    10.100.100.13 is the default n6 at PSA-UPF-1.
