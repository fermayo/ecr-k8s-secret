# AWS ECR credential secret generator for Kubernetes

Automatically creates a Kubernetes secret to pull images from AWS ECR using your AWS credentials

## Usage

Requirements:
* Configured `aws` CLI
* Configured `kubectl` CLI

Run:

    curl -LSs https://github.com/fermayo/ecr-k8b-secret/raw/master/gen-secret.sh | bash -


This will automatically create a secret called `aws-ecr-credentials` that you can use on your Pod definition:

    spec:
      imagePullSecrets:
        - name: aws-ecr-credentials
      [...]

Remember that AWS ECR login credentials expire in 12 hours!

More info at https://kubernetes.io/docs/tasks/configure-pod-container/pull-image-private-registry/
