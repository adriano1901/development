

`flux check --pre`

````sh

flux bootstrap github \
  --token-auth \
  --owner=adriano1901 \
  --repository=development \
  --path=kubernetes/fluxcd/repositories/infra-repo/clusters/dev-cluster \
  --personal \
  --branch main
````

flux check

# flux manages itself using GitOps objects:

kubectl -n flux-system get GitRepository
kubectl -n flux-system get Kustomization

## automate deploy by image scanning

````sh

flux bootstrap github \
  --token-auth \
  --owner=adriano1901 \
  --repository=development \
  --path=kubernetes/fluxcd/repositories/infra-repo/clusters/dev-cluster \
  --components-extra=image-reflector-controller,image-automation-controller \
  --personal \
  --branch main
````