<!-- BEGIN_TF_DOCS -->
# Access Leaf Switch Profile Example

To run this example you need to execute:

```bash
$ terraform init
$ terraform plan
$ terraform apply
```

Note that this example will create resources. Resources can be destroyed with `terraform destroy`.

```hcl
module "aci_access_leaf_switch_profile" {
  source  = "netascode/access-leaf-switch-profile/aci"
  version = ">= 0.2.0"

  name               = "LEAF101"
  interface_profiles = ["PROF1"]
  selectors = [{
    name         = "SEL1"
    policy_group = "POL1"
    node_blocks = [{
      name = "BLOCK1"
      from = 101
      to   = 101
    }]
  }]
}
```
<!-- END_TF_DOCS -->