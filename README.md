# Install CLI tooling

The following command will install the Istio 1.0.0 release.
```sh
curl -L https://git.io/getLatestIstio | ISTIO_VERSION=1.0.0 sh -
```

After it has successfully run, add the bin folder to your path.
```sh
export PATH="$PATH:/root/istio-1.0.0/bin"
cd /root/istio-1.0.0
```

Configure Istio CRD

Istio has extended Kubernetes via Custom Resource Definitions (CRD). Deploy the extensions by applying crds.yaml.

kubectl apply -f install/kubernetes/helm/istio/templates/crds.yaml -n istio-system
Install Istio with default mutual TLS authentication

To Install Istio and enforce mutual TLS authentication by default, use the yaml istio-demo-auth.yaml:

kubectl apply -f install/kubernetes/istio-demo-auth.yaml