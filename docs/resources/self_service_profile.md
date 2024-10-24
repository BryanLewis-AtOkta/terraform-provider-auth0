---
page_title: "Resource: auth0_self_service_profile"
description: |-
  With this resource, you can create and manage Self-Service Profile for a tenant.
---

# Resource: auth0_self_service_profile

With this resource, you can create and manage Self-Service Profile for a tenant.

## Example Usage

```terraform
resource "auth0_self_service_profile" "my_self_service_profile" {
  user_attributes {
    name        = "sample-name"
    description = "sample-description"
    is_optional = true
  }
  branding {
    logo_url = "https://mycompany.org/v2/logo.png"
    colors {
      primary = "#0059d6"
    }
  }
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Optional

- `branding` (Block List, Max: 1) Field can be used to customize the look and feel of the wizard. (see [below for nested schema](#nestedblock--branding))
- `user_attributes` (Block List, Max: 20) This array stores the mapping information that will be shown to the user during the SS-SSO flow. The user will be prompted to map the attributes on their identity provider to ensure the specified attributes get passed to Auth0. (see [below for nested schema](#nestedblock--user_attributes))

### Read-Only

- `created_at` (String) The ISO 8601 formatted date the profile was created.
- `id` (String) The ID of this resource.
- `updated_at` (String) The ISO 8601 formatted date the profile was updated.

<a id="nestedblock--branding"></a>
### Nested Schema for `branding`

Optional:

- `colors` (Block List, Max: 1) Configuration settings for colors for branding. (see [below for nested schema](#nestedblock--branding--colors))
- `logo_url` (String) URL of logo to display on login page.

<a id="nestedblock--branding--colors"></a>
### Nested Schema for `branding.colors`

Optional:

- `primary` (String) Primary button background color in hexadecimal.



<a id="nestedblock--user_attributes"></a>
### Nested Schema for `user_attributes`

Required:

- `description` (String) A human readable description of the attribute.
- `is_optional` (Boolean) Indicates if this attribute is optional or if it has to be provided by the customer for the application to function.
- `name` (String) Attribute’s name on Auth0 side

## Import

Import is supported using the following syntax:

```shell
# This resource can be imported using the id
# Example:
terraform import auth0_self_service_profile.id "ssp_32oi5unksja93124"
```