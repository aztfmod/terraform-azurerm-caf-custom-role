[![VScodespaces](https://img.shields.io/endpoint?url=https%3A%2F%2Faka.ms%2Fvso-badge)](https://online.visualstudio.com/environments/new?name=terraform-azurerm-caf-custom-role&repo=aztfmod/terraform-azurerm-caf-custom-role)

# Deploy custom roles and assign to subscriptions

This module creates a set of custom roles and assigns them to a subscription.

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| aad\_apps | Map of aad\_app objects that could be associated to a subscription | `any` | n/a | yes |
| custom\_role\_definition | n/a | <pre>object({<br>    name        = string<br>    convention  = string<br>    description = string<br>    useprefix   = bool<br>    scope = object({<br>      subscriptions_keys = string<br>      explicit_scope     = string<br>    })<br>    assignable_scopes = list(string)<br>    permissions = object({<br>      actions          = list(string)<br>      not_actions      = list(string)<br>      data_actions     = list(string)<br>      not_data_actions = list(string)<br>    })<br>    mapping_subscription_key_to_azure_app_keys = map(string)<br>  })</pre> | <pre>{<br>  "assignable_scopes": [],<br>  "convention": "cafrandom",<br>  "description": "",<br>  "mapping_subscription_key_to_azure_app_keys": {},<br>  "name": "",<br>  "permissions": {<br>    "actions": [],<br>    "data_actions": [],<br>    "not_actions": [<br>      "*"<br>    ],<br>    "not_data_actions": []<br>  },<br>  "scope": {<br>    "explicit_scope": "",<br>    "subscriptions_keys": ""<br>  },<br>  "useprefix": false<br>}</pre> | no |
| custom\_role\_definitions | Map of custom\_role\_definition object as defined in the custom\_role\_definition | `any` | n/a | yes |
| prefix | n/a | `string` | `""` | no |
| subscriptions | Map of subscriptions | `any` | n/a | yes |

## Outputs

| Name | Description |
|------|-------------|
| azurecaf\_naming\_convention | n/a |
| custom\_role\_definitions | n/a |