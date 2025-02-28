---
layout: "ibm"
page_title: "IBM : ibm_cd_toolchain_tool_pagerduty"
description: |-
  Get information about cd_toolchain_tool_pagerduty
subcategory: "CD Toolchain"
---

# ibm_cd_toolchain_tool_pagerduty

~> **Beta:** This data source is in Beta, and is subject to change.

Provides a read-only data source for cd_toolchain_tool_pagerduty. You can then reference the fields of the data source in other resources within the same configuration using interpolation syntax.

## Example Usage

```hcl
data "ibm_cd_toolchain_tool_pagerduty" "cd_toolchain_tool_pagerduty" {
	tool_id = "tool_id"
	toolchain_id = ibm_cd_toolchain_tool_pagerduty.cd_toolchain_tool_pagerduty.toolchain_id
}
```

## Argument Reference

Review the argument reference that you can specify for your data source.

* `tool_id` - (Required, Forces new resource, String) ID of the tool bound to the toolchain.
  * Constraints: The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/^[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-4[a-fA-F0-9]{3}-[89abAB][a-fA-F0-9]{3}-[a-fA-F0-9]{12}$/`.
* `toolchain_id` - (Required, Forces new resource, String) ID of the toolchain.
  * Constraints: The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/^[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-4[a-fA-F0-9]{3}-[89abAB][a-fA-F0-9]{3}-[a-fA-F0-9]{12}$/`.

## Attribute Reference

In addition to all argument references listed, you can access the following attribute references after your data source is created.

* `id` - The unique identifier of the cd_toolchain_tool_pagerduty.
* `crn` - (Required, String) Tool CRN.


* `href` - (Required, String) URI representing the tool.

* `name` - (Optional, String) Tool name.

* `parameters` - (Required, List) Parameters to be used to create the tool.
Nested scheme for **parameters**:
	* `api_key` - (Optional, String) Type your API access key. You can find or create this key on the Configuration/API Access section of the PagerDuty website. [PagerDuty Support article on how to get API Key](https://support.pagerduty.com/hc/en-us/articles/202829310-Generating-an-API-Key).
	* `key_type` - (Required, String) Select whether to integrate at the account level with an API key or at the service level with an integration key.
	  * Constraints: Allowable values are: `api`, `service`.
	* `service_id` - (Optional, String) service_id.
	* `service_key` - (Optional, String) Type your integration key. You can find or create this key in the Integrations section of the PagerDuty service page.
	* `service_name` - (Optional, String) Type the name of the PagerDuty service to post alerts to. If you want alerts to be posted to a new service, type a new name. PagerDuty will create the service.
	* `service_url` - (Optional, String) Type the URL of the PagerDuty service to post alerts to.
	* `user_email` - (Optional, String) Type the email address of the user to contact when an alert is posted. If you want alerts to be sent to a new email address, type the address and PagerDuty will create a user.
	* `user_phone` - (Optional, String) Type the phone number of the user to contact when an alert is posted. Include the national code followed by a space and a 10-digit number; for example: +1 1234567890. If you omit the national code, it is set to +1 by default.

* `referent` - (Required, List) Information on URIs to access this resource through the UI or API.
Nested scheme for **referent**:
	* `api_href` - (Optional, String) URI representing the this resource through an API.
	* `ui_href` - (Optional, String) URI representing the this resource through the UI.

* `resource_group_id` - (Required, String) Resource group where tool can be found.

* `state` - (Required, String) Current configuration state of the tool.
  * Constraints: Allowable values are: `configured`, `configuring`, `misconfigured`, `unconfigured`.

* `toolchain_crn` - (Required, String) CRN of toolchain which the tool is bound to.

* `updated_at` - (Required, String) Latest tool update timestamp.

