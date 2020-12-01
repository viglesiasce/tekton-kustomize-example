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

1. Install Kustomize plugin

    ```shell
    mkdir -p ~/.config/kustomize/plugin/pipelinerunsuffix.tekton.cd/pipelinerunsuffixgenerator
    cp kustomize-plugin/PipelineRunSuffixGenerator ~/.config/kustomize/plugin/pipelinerunsuffix.tekton.cd/v1/pipelinerunsuffixgenerator
    ```

1. Apply config

    ```shell
    skaffold dev
    ```


