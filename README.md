1. Install deps

    ```shell
    gcloud components install minikube kubectl kpt skaffold
    ```

1. Start K8s cluster

    ```shell
    minikube start
    ```

1. Apply config

    ```shell
    kpt live apply .
    ```

1. Port forward to Tekton Dashboard

    ```shell
    kubectl --namespace tekton-pipelines port-forward svc/tekton-dashboard 9097:9097
    ```

1. Create Docker registry secret:

    ```shell
    kubectl create secret generic regcred  --from-file=.dockerconfigjson --type=kubernetes.io/dockerconfigjson
    ```

1. Run pipeline:

    ```shell
    tkn pipeline start build-image --use-pipelinerun build-image-default --serviceaccount tutorial-service --showlog
    ```