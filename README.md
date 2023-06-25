# vault

# Generate vault manifest from helm

```bash
helm repo add hashicorp https://helm.releases.hashicorp.com
helm fetch --untar --untardir charts hashicorp/vault
mkdir base
helm template --output-dir base --namespace vault --values ha-override-values.yaml vault charts/vault
mkdir -p kustomize/base/vault
cp base/vault/templates/*.yaml kustomize/base/vault/
```

