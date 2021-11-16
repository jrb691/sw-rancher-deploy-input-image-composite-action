# Deploy to Rancher Cluster - Input Image Tag
Use if you want to be able to manually input what image tag to deploy into rancher.

### Parameters: 
Name | Type |        | Default | Notes |
---  | ---  | ---------- | ------- | ---- |
`environment` | String | Required* | `dev`
`np_kube_config_data` | Secret | Required* |
`prod_kube_config_data` | Secret | Required* |
`image_tag` | String | Required* | 
`jf_artifactory_token` | Secret | *Optional* | | You must provide this parameter if you are using JFrog Artifactory*
`labels_path`| String | *Optional* | 
`deployment_yaml_path` | Path | *Optional* | `kubernetes/deployment.yml`
`namespace` | String | *Optional* | `gitactions`
`files`| String | *Optional* | `kubernetes/.`
`image_registry_provider` | String | *Optional* | `artifactory` | Use this parameter to the skip docker artifactory image promotion step.

Usage:
```yaml
      - uses: sherwin-williams-co/sw-rancher-deploy-input-image-composite-action@main
        with:
          environment: dev
          np_kube_config_data: ${{ secrets.KUBE_CONFIG_NP_RANCHER }}
          prod_kube_config_data: ${{ secrets.KUBE_CONFIG_PROD_RANCHER }}
          image_tag: ${{ github.event.inputs.image_tag }}
          # Optional
          # jf_artifactory_token: ${{ secrets.JF_ARTIFACTORY_TOKEN }}
          # labels_path: 'kubernetes/labels'
          # deployment_yaml_path: 'kubernetes/deployment.yml'
          # namespace: 'gitactions'
          # files: 'kubernetes/.'
          # image_registry_provider: acr
```
