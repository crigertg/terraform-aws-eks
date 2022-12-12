<!-- BEGINNING OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
## Example
This is an example of usage `weave-scope` module

```
module "weave-scope" {
  count            = var.weave_scope_enabled ? 1 : 0
  source           = "./modules/weave-scope"

  namespace        = "Weave"
  create_namespace = true
  ingress_class = "nginx"
  ingress_host = "www.example.com"
  annotations = {
    "key1" = "value1"
    "key2" = "value2"
  }
  service_type = "NodePort"

}

provider "helm" {
  kubernetes {
    host                   = cluster.host
    cluster_ca_certificate = cluster.certificate
    token                  = cluster.token
  }
}
```
**/

## Requirements

| Name | Version |
|------|---------|
| <a name="requirement_helm"></a> [helm](#requirement\_helm) | >= 2.0 |

## Providers

| Name | Version |
|------|---------|
| <a name="provider_helm"></a> [helm](#provider\_helm) | >= 2.0 |

## Modules

No modules.

## Resources

| Name | Type |
|------|------|
| [helm_release.weave-scope](https://registry.terraform.io/providers/hashicorp/helm/latest/docs/resources/release) | resource |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_annotations"></a> [annotations](#input\_annotations) | Annotations to pass, used for Ingress configuration | `map(string)` | `{}` | no |
| <a name="input_chart_version"></a> [chart\_version](#input\_chart\_version) | Weave Scope chart version | `string` | `"1.0.2"` | no |
| <a name="input_create_namespace"></a> [create\_namespace](#input\_create\_namespace) | Weather create namespace or not | `bool` | `true` | no |
| <a name="input_ingress_class"></a> [ingress\_class](#input\_ingress\_class) | Ingress class name used for Ingress configuration | `string` | `""` | no |
| <a name="input_ingress_host"></a> [ingress\_host](#input\_ingress\_host) | Ingress host name used for Ingress configuration | `string` | `""` | no |
| <a name="input_ingress_name"></a> [ingress\_name](#input\_ingress\_name) | Ingress name to configure in helm chart | `string` | `"weave-ingress"` | no |
| <a name="input_namespace"></a> [namespace](#input\_namespace) | Kubernetes namespace, in which Weave Scope will be deployed | `string` | `"meta-system"` | no |
| <a name="input_read_only"></a> [read\_only](#input\_read\_only) | Whether to disable write operations in weave frontend | `bool` | `false` | no |
| <a name="input_release_name"></a> [release\_name](#input\_release\_name) | Helm chart release name | `string` | `"weave-scope"` | no |
| <a name="input_service_type"></a> [service\_type](#input\_service\_type) | Service type configuration Valid attributes are NodePort, LoadBalancer, ClusterIP | `string` | `"ClusterIP"` | no |
| <a name="input_weave_scope_image_version"></a> [weave\_scope\_image\_version](#input\_weave\_scope\_image\_version) | Weave Scope image version | `string` | `"1.10.1"` | no |

## Outputs

No outputs.
<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
