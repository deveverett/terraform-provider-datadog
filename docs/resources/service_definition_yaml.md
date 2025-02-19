---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "datadog_service_definition_yaml Resource - terraform-provider-datadog"
subcategory: ""
description: |-
  Provides a Datadog service definition resource. This can be used to create and manage Datadog service definitions in the service catalog using the YAML/JSON definition.
---

# datadog_service_definition_yaml (Resource)

Provides a Datadog service definition resource. This can be used to create and manage Datadog service definitions in the service catalog using the YAML/JSON definition.

## Example Usage

```terraform
resource "datadog_service_definition_yaml" "service_definition" {
  service_definition = <<EOF
schema-version: v2
dd-service: shopping-cart
team: E Commerce
contacts:
  - name: Support Email
    type: email
    contact: team@shopping.com
  - name: Support Slack
    type: slack
    contact: https://www.slack.com/archives/shopping-cart
repos:
  - name: shopping-cart source code
    provider: github
    url: http://github/shopping-cart
docs:
  - name: shopping-cart architecture
    provider: gdoc
    url: https://google.drive/shopping-cart-architecture
  - name: shopping-cart service Wiki
    provider: wiki
    url: https://wiki/shopping-cart
links:
  - name: shopping-cart runbook
    type: runbook
    url: https://runbook/shopping-cart
tags:
  - business-unit:retail
  - cost-center:engineering
integrations:
  pagerduty: https://www.pagerduty.com/service-directory/Pshopping-cart
extensions:
  datadoghq.com/shopping-cart:
    customField: customValue
EOF
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `service_definition` (String) The YAML/JSON formatted definition of the service

### Read-Only

- `id` (String) The ID of this resource.

## Import

Import is supported using the following syntax:

```shell
terraform import datadog_service_definition_yaml.service_definition "<dd-service>"
```
