# Deploy to Rancher Cluster - Input Image Tag
Use if you want to be able to manually input what image you wish to deploy into rancher.

### Parameters: 
Name | Type |        | Default |
---  | ---  | ---------- | ------- |
`environment` | String | Required* | `dev`
`kube_config_data` | Secret | Required* |
`image_tag` | String | Required* | 
`labels_path`| String | *Optional* | 
`deployment_yaml_path` | Path | *Optional* | `kubernetes/deployment.yml`
`namespace` | String | *Optional* | `gitactions`
`files`| String | *Optional* | `kubernetes/.`

Usage:
```yaml
      - uses: sherwin-williams-co/sw-rancher-deploy-input-image-composite-action@main
        with:
          environment: dev
          kube_config_data: ${{ secrets.KUBE_CONFIG_NP_RANCHER }}
          image_tag: ${{ github.event.inputs.image_tag }}
          # Optional
          # labels_path: 'kubernetes/labels'
          # deployment_yaml_path: 'kubernetes/deployment.yml'
          # namespace: 'gitactions'
          # files: 'kubernetes/.'
```
