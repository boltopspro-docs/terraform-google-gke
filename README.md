<!-- note marker start -->
**NOTE**: This repo contains only the documentation for the private BoltsOps Pro repo code.
Original file: https://github.com/boltopspro/terraform-google-gke/blob/master/README.md
The docs are publish so they are available for interested customers.
For access to the source code, you must be a paying BoltOps Pro subscriber.
If are interested, you can contact us at contact@boltops.com or https://www.boltops.com

<!-- note marker end -->

## GKE Cluster

Configure tfvars for the gke stack.

    app/stacks/gke/tfvars
    └── dev
        ├── base.tfvars
        ├── cluster-1.tfvars
        └── cluster-2.tfvars

The tfvars structure leverages the [Terraspace Instance Option](https://terraspace.cloud/docs/tfvars/instance-option/) to use the same code to create different gke clusters.

## Examples

    terraspace up gke
    terraspace up gke -i cluster-1
    terraspace up gke -i cluster-2

![](https://img.boltops.com/images/modules/gke/gke.png)

Add more tfvars files to create more gke clusters with different settings like cluster and service IP Ranges.

## Known Issues

* When updating the GKE ranges, Terraform will destroy the node pool but not create it. We have to run terraform a second time and then the node pool gets created fine. This only occurs when the IP ranges are changed.
