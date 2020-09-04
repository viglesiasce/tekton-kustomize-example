1. Install deps

    ```shell
    gcloud components install minikube kubectl kustomize skaffold
    ```

1. Start K8s cluster

    ```shell
    minikube start
    ```

1. Copy Registry credentials:

    ```shell
    cp ~/.docker/config.json .dockerconfigjson
    ```

1. Apply config

    ```shell
    skaffold dev
    ```
