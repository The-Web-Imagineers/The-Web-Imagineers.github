Represents a business on Facebook. Includes any specified properties and assets belonging to the business.

Starting September 14, 2021, the following fields will throw an error for version 12.0+ calls made by apps that lack the endpoint's required permissions. This change will apply to all versions on December 13, 2021.

collaborative_ads_managed_partner_business_info
Example
HTTPPHP SDKJavaScript SDKAndroid SDKiOS SDKGraph API Explorer
GET /v19.0/{business-id} HTTP/1.1
Host: graph.facebook.com
If you want to learn how to use the Graph API, read our Using Graph API guide.
Parameters
This endpoint doesn't have any parameters.
Fields
Field	Description
id
numeric string
The business account ID.

Default
block_offline_analytics
bool
Specifies whether offline analytics for business is blocked.

collaborative_ads_managed_partner_business_info
ManagedPartnerBusiness
collaborative_ads_managed_partner_business_info

collaborative_ads_managed_partner_eligibility
BusinessManagedPartnerEligibility
collaborative_ads_managed_partner_eligibility

created_by
BusinessUser|SystemUser
The creator of this business.

created_time
datetime
The creation time of this business.

extended_updated_time
datetime
The update time of the extended credits for this business.

is_hidden
bool
If true, indicates the business is hidden.

link
string
URI for business profile page.

name
string
The name of the business.

Default
payment_account_id
numeric string
The ID for the payment account of this business.

primary_page
Page
The primary Facebook Page for this business.

profile_picture_uri
string
The profile picture URI of the business.

timezone_id
unsigned int32
This business's timezone.

two_factor_type
enum
The two factor type authentication used for this business.

updated_by
BusinessUser|SystemUser
The person's name who last updated this business.

updated_time
datetime
The time when this business was last updated.

verification_status
enum
Verification status for this business.

vertical
string
The vertical industry that this business associates with, or belongs to.

vertical_id
unsigned int32
The ID for the vertical industry.

Edges
Edge	Description
ad_studies
The studies this business has access to, such as any advertising lift studies or split testing studies.

adnetworkanalytics
Audience Network query for this publisher entity.

adnetworkanalytics_results
Obtain the results of an asynchronous Audience Network query for this publisher entity.

ads_reporting_mmm_reports
Marketing mix modeling (MMM) reports generated for this business

ads_reporting_mmm_schedulers
Marketing mix modeling (MMM) reports schedulers for this business

adspixels
The business has access to these pixels.

agencies
Agencies associated with this business.

an_placements
Placements used by this Audience Network business.

business_asset_groups
Business asset groups owned by this business. The business can grant permissions to assets in this group.

business_invoices
The extended credit invoices of this business.

business_users
Business users associated with this business. Includes employees and admins at the business.

client_ad_accounts
This business has access to these client ad accounts.

client_apps
This business has access to these client apps.

client_offsite_signal_container_business_objects
The business has access to these client offsite signal container business objects

client_pages
This business has access to these client pages.

client_pixels
This business has access to these client pixels.

client_product_catalogs
This business has access to these client product catalogs.

client_whatsapp_business_accounts
WhatsApp business accounts that were shared to this business.

clients
Clients of this business.

collaborative_ads_collaboration_requests
All Collaborative Ads. collaboration requests initiated by the business.

collaborative_ads_suggested_partners
Collaborative Ads suggested partners for a business.

commerce_merchant_settings
Commerce Merchant Settings belonging to this business.

event_source_groups
The business owns these event source groups. Includes various signals sources such as pixels.

extendedcredits
Extended credits for this business.

initiated_audience_sharing_requests
The audience sharing requests initiated by this business.

instagram_accounts
This business has access to these Instagram accounts.

instagram_business_accounts
Instagram accounts already converted into business accounts. These accounts have an associated business user.

measurement_reports
The measurement reports that the business owns.

offline_conversion_data_sets
The business has access to these offline conversion datasets.

openbridge_configurations
Get all the openbridge configurations associated to this business

owned_ad_accounts
This business owns these ad accounts.

owned_apps
This business owns these apps.

owned_businesses
This business aggregates and manages these client businesses.

owned_instagram_accounts
This business owns these Instagram accounts.

owned_offsite_signal_container_business_objects
owned_offsite_signal_container_business_objects

owned_pages
This business owns these pages.

owned_pixels
This business owns these pixels.

owned_product_catalogs
This business owns these product catalogs.

owned_whatsapp_business_accounts
This business owns these WhatsApp Business Accounts.

pending_client_ad_accounts
This business requested access to these client ad accounts and is pending approval.

pending_client_apps
This business requested access to these client apps and is pending approval.

pending_client_pages
This business requested access to these client pages and is pending approval.

pending_owned_ad_accounts
This business requested ownership of these ad accounts and is pending approval.

pending_owned_pages
This business requested ownership of these pages and is pending approval.

pending_shared_offsite_signal_container_business_objects
This business received sharing requests for these offsite signal container business objects and is pending for approval.

pending_users
Admin for this business invited this user to the business. Pending user approval.

preverified_numbers
Edge to get list of all pre-created phone numbers for this business

received_audience_sharing_requests
The audience sharing requests received by this business.

system_users
The business's system users.

Error Codes
Error	Description
100	Invalid parameter
200	Permissions error
368	The action attempted has been deemed abusive or is otherwise disallowed
190	Invalid OAuth 2.0 Access Token
80004	There have been too many calls to this ad-account. Wait a bit and try again. For more info, please refer to https://developers.facebook.com/docs/graph-api/overview/rate-limiting#ads-management.
2635	You are calling a deprecated version of the Ads API. Please update to the latest version.
131000	Something went wrong
Creating
To create other Business Managers, your business needs to obtain BUSINESS_MANAGEMENT during the app review process. If your app is in development mode, you can surpass this requirement, but to create only two child businesses.

You can make a POST request to agencies edge from the following paths:
/{offline_conversion_data_set_id}/agencies
When posting to this edge, a Business will be created.
Parameters
Parameter	Description
business
numeric string or integer
SELF_EXPLANATORY

Required
other_relationship
string
SELF_EXPLANATORY

permitted_roles
list<enum {ADMIN, UPLOADER, ADVERTISER}>
Permitted roles the agency can assign to users

relationship_type
array<enum {AD_MANAGER, AUDIENCE_MANAGER, AGENCY, AGGREGATOR, OTHER}>
Relationship type for sharing

Return Type
This endpoint supports read-after-write and will read the node to which you POSTed.
Struct {
success: bool,
share_status: enum,
}
Error Codes
Error	Description
3989	You are trying to assign a duplicated asset to this agency.
You can make a POST request to china_business_onboarding_attributions edge from the following paths:
/{business_id}/china_business_onboarding_attributions
When posting to this edge, a Business will be created.
Parameters
This endpoint doesn't have any parameters.
Return Type
Struct {
id: numeric string,
link_with_id: string,
}
Error Codes
Error	Description
200	Permissions error
You can make a POST request to businesses edge from the following paths:
/{user_id}/businesses
When posting to this edge, a Business will be created.
Parameters
Parameter	Description
child_business_external_id
string
child_business_external_id

email
string
The business email of the business admin

name
string
Username

Required
primary_page
page ID
Primary Page ID

sales_rep_email
string
Sales Rep email address

survey_business_type
enum {AGENCY, ADVERTISER, APP_DEVELOPER, PUBLISHER}
Business Type

survey_num_assets
int64
Number of Assets in the business

survey_num_people
int64
Number of People that will work on the business

timezone_id
int64
Timezone ID

vertical
enum {NOT_SET, ADVERTISING, AUTOMOTIVE, CONSUMER_PACKAGED_GOODS, ECOMMERCE, EDUCATION, ENERGY_AND_UTILITIES, ENTERTAINMENT_AND_MEDIA, FINANCIAL_SERVICES, GAMING, GOVERNMENT_AND_POLITICS, MARKETING, ORGANIZATIONS_AND_ASSOCIATIONS, PROFESSIONAL_SERVICES, RETAIL, TECHNOLOGY, TELECOM, TRAVEL, NON_PROFIT, RESTAURANT, HEALTH, LUXURY, OTHER}
Vertical ID

Required
Return Type
This endpoint supports read-after-write and will read the node represented by id in the return type.
Struct {
id: numeric string,
}
Error Codes
Error	Description
100	Invalid parameter
368	The action attempted has been deemed abusive or is otherwise disallowed
42000	This Page can't be added because it's already linked to an Instagram business profile. To add this Page to Business Manager, go to Instagram and convert to a personal account or change the Page linked to your business profile.
3918	The Facebook Page you've tried to add is already owned by another Business Manager. You can still request access to this Page, but your request will need to be approved by the Business Manager that owns it.
3974	The name you chose for this Business Manager is not valid. Try a different name.
3947	You are trying to create a Business Manager with the same name as one you are already a part of. Please pick a different name.
3913	It doesn't look like you have permission to create a new Business Manager.
3912	There was a technical issue and the changes you made to your Business Manager weren't saved. Please try again.
3973	The name you chose for this Business Manager is not valid. Please choose another.
3998	You must be an admin of the primary Page to create a business using that page.
You can make a POST request to owned_businesses edge from the following paths:
/{business_id}/owned_businesses
When posting to this edge, a Business will be created.
Parameters
Parameter	Description
name
string
name

Required
page_permitted_tasks
array<enum {MANAGE, CREATE_CONTENT, MODERATE, MESSAGING, ADVERTISE, ANALYZE, MODERATE_COMMUNITY, MANAGE_JOBS, PAGES_MESSAGING, PAGES_MESSAGING_SUBSCRIPTIONS, READ_PAGE_MAILBOXES, VIEW_MONETIZATION_INSIGHTS, MANAGE_LEADS, PROFILE_PLUS_FULL_CONTROL, PROFILE_PLUS_MANAGE, PROFILE_PLUS_FACEBOOK_ACCESS, PROFILE_PLUS_CREATE_CONTENT, PROFILE_PLUS_MODERATE, PROFILE_PLUS_MODERATE_DELEGATE_COMMUNITY, PROFILE_PLUS_MESSAGING, PROFILE_PLUS_ADVERTISE, PROFILE_PLUS_ANALYZE, PROFILE_PLUS_REVENUE, PROFILE_PLUS_MANAGE_LEADS, CASHIER_ROLE}>
page_permitted_tasks

sales_rep_email
string
sales_rep_email

shared_page_id
page ID
shared_page_id

survey_business_type
enum {AGENCY, ADVERTISER, APP_DEVELOPER, PUBLISHER}
survey_business_type

survey_num_assets
int64
survey_num_assets

survey_num_people
int64
survey_num_people

timezone_id
int64
timezone_id

vertical
enum {NOT_SET, ADVERTISING, AUTOMOTIVE, CONSUMER_PACKAGED_GOODS, ECOMMERCE, EDUCATION, ENERGY_AND_UTILITIES, ENTERTAINMENT_AND_MEDIA, FINANCIAL_SERVICES, GAMING, GOVERNMENT_AND_POLITICS, MARKETING, ORGANIZATIONS_AND_ASSOCIATIONS, PROFESSIONAL_SERVICES, RETAIL, TECHNOLOGY, TELECOM, TRAVEL, NON_PROFIT, RESTAURANT, HEALTH, LUXURY, OTHER}
vertical

Required
Return Type
This endpoint supports read-after-write and will read the node represented by id in the return type.
Struct {
id: numeric string,
}
Error Codes
Error	Description
200	Permissions error
100	Invalid parameter
3913	It doesn't look like you have permission to create a new Business Manager.
3947	You are trying to create a Business Manager with the same name as one you are already a part of. Please pick a different name.
3974	The name you chose for this Business Manager is not valid. Try a different name.
457	The session has an invalid origin
Updating
You can update a Business by making a POST request to /{business_id}.
Parameters
Parameter	Description
entry_point
string
entry point of claiming BusinessClaimAssetEntryPoint

name
string
Business's name

primary_page
numeric string or integer
Primary page of this business

timezone_id
int64
Timezone id of this business

two_factor_type
enum{none, admin_required, all_required}
Two-factor type of the business

vertical
enum {NOT_SET, ADVERTISING, AUTOMOTIVE, CONSUMER_PACKAGED_GOODS, ECOMMERCE, EDUCATION, ENERGY_AND_UTILITIES, ENTERTAINMENT_AND_MEDIA, FINANCIAL_SERVICES, GAMING, GOVERNMENT_AND_POLITICS, MARKETING, ORGANIZATIONS_AND_ASSOCIATIONS, PROFESSIONAL_SERVICES, RETAIL, TECHNOLOGY, TELECOM, TRAVEL, NON_PROFIT, RESTAURANT, HEALTH, LUXURY, OTHER}
Vertical type of the business

Return Type
This endpoint supports read-after-write and will read the node represented by id in the return type.
Struct {
id: numeric string,
}
Error Codes
Error	Description
3974	The name you chose for this Business Manager is not valid. Try a different name.
3910	You need permission to edit the details of your Business Manager. Please talk to one of your Business Manager admins about changing your role or editing the Business Manager details.
3973	The name you chose for this Business Manager is not valid. Please choose another.
3911	You need permission to set up a new Business Manager.
3947	You are trying to create a Business Manager with the same name as one you are already a part of. Please pick a different name.
3912	There was a technical issue and the changes you made to your Business Manager weren't saved. Please try again.
3918	The Facebook Page you've tried to add is already owned by another Business Manager. You can still request access to this Page, but your request will need to be approved by the Business Manager that owns it.
100	Invalid parameter
457	The session has an invalid origin
190	Invalid OAuth 2.0 Access Token
You can update a Business by making a POST request to /{business_id}/managed_businesses.
Parameters
Parameter	Description
child_business_external_id
string
child_business_external_id

existing_client_business_id
business ID
Existing client business id provided by the client

name
string
Client business name that's managed by the aggregator business

sales_rep_email
string
Email of sales representative of the business that's managed by the aggregator business

survey_business_type
enum {AGENCY, ADVERTISER, APP_DEVELOPER, PUBLISHER}
Business type of surveyed business that's managed by the aggregator business

survey_num_assets
int64
Number of assets surveyed of business that's managed by the aggregator business

survey_num_people
int64
Number of people surveyed of business that's managed by the aggregator business

timezone_id
int64
Timezone id of business that's managed by the aggregator business

vertical
enum {NOT_SET, ADVERTISING, AUTOMOTIVE, CONSUMER_PACKAGED_GOODS, ECOMMERCE, EDUCATION, ENERGY_AND_UTILITIES, ENTERTAINMENT_AND_MEDIA, FINANCIAL_SERVICES, GAMING, GOVERNMENT_AND_POLITICS, MARKETING, ORGANIZATIONS_AND_ASSOCIATIONS, PROFESSIONAL_SERVICES, RETAIL, TECHNOLOGY, TELECOM, TRAVEL, NON_PROFIT, RESTAURANT, HEALTH, LUXURY, OTHER}
Business vertical of business that's managed by the aggregator business

Return Type
This endpoint supports read-after-write and will read the node represented by id in the return type.
Struct {
id: numeric string,
}
Error Codes
Error	Description
42004	You couldn't create the client business on behalf your client successfully
100	Invalid parameter
200	Permissions error
Deleting
You can dissociate a Business from a Business by making a DELETE request to /{business_id}/agencies.
Parameters
Parameter	Description
business
numeric string or integer
The agency's business.

Required
Return Type
Struct {
success: bool,
}
Error Codes
Error	Description
100	Invalid parameter
You can dissociate a Business from a Business by making a DELETE request to /{business_id}/clients.
Parameters
Parameter	Description
business
numeric string or integer
The client's business.

Required
Return Type
Struct {
success: bool,
}
Error Codes
Error	Description
100	Invalid parameter
You can dissociate a Business from a Business by making a DELETE request to /{business_id}/pages.
Parameters
Parameter	Description
page_id
Page ID
Page ID.

Required
Return Type
Struct {
success: bool,
}
Error Codes
Error	Description
42001	This Page can't be removed because it's already linked to an Instagram business profile. To remove this Page from Business Manager, go to Instagram and convert to a personal account or change the Page linked to your business profile.
3948	Please assign someone as a manager to this Page before removing it from your Business Manager.
3996	The page does not belong to this Business Manager.
100	Invalid parameter
200	Permissions error
457	The session has an invalid origin
190	Invalid OAuth 2.0 Access Token
You can dissociate a Business from a Business by making a DELETE request to /{business_id}/instagram_accounts.
Parameters
Parameter	Description
instagram_account
Instagram account/Instagram account v2 ID
Instagram account ID.

Required
Return Type
Struct {
success: bool,
}
Error Codes
Error	Description
100	Invalid parameter
457	The session has an invalid origin
200	Permissions error
You can dissociate a Business from a Business by making a DELETE request to /{business_id}/ad_accounts.
Parameters
Parameter	Description
adaccount_id
string
Ad account ID.

Required
Return Type
Struct {
success: bool,
}
Error Codes
Error	Description
100	Invalid parameter
457	The session has an invalid origin
200	Permissions error
190	Invalid OAuth 2.0 Access Token
You can dissociate a Business from a Business by making a DELETE request to /{business_id}/owned_businesses.
Parameters
Parameter	Description
client_id
business ID
client_id

Required
Return Type
Struct {
success: bool,
}
Error Codes
Error	Description
3912	There was a technical issue and the changes you made to your Business Manager weren't saved. Please try again.
100	Invalid parameter
200	Permissions error
You can dissociate a Business from an AdAccount by making a DELETE request to /act_{ad_account_id}/agencies.
Parameters
Parameter	Description
business
business ID
SELF_EXPLANATORY

Required
Return Type
Struct {
success: bool,
}
Error Codes
Error	Description
100	Invalid parameter
200	Permissions error
457	The session has an invalid origin
You can dissociate a Business from a User by making a DELETE request to /{user_id}/businesses.
Parameters
Parameter	Description
business
numeric string or integer
Business ID

Return Type
Struct {
success: bool,
}
Error Codes
Error	Description
3914	It looks like you're trying to remove the last admin from this Business Manager. At least one admin is required in Business Manager.
100	Invalid parameter
190	Invalid OAuth 2.0 Access Token## Hi there 👋

<!--

**Here are some ideas to get you started:**

🙋‍♀️ A short introduction - what is your organization all about?
🌈 Contribution guidelines - how can the community get involved?
👩‍💻 Useful resources - where can the community find your docs? Is there anything else the community should know?
🍿 Fun facts - what does your team eat for breakfast?
🧙 Remember, you can do mighty things with the power of [Markdown](https://docs.github.com/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
-->
