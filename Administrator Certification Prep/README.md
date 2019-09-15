* [Set Up and Maintain Your Salesforce Organization](https://help.salesforce.com/articleView?id=setup_overview.htm&type=5)

* Formula fields are the preferred choice when child record fields need to be populated with the parent record field information.
* Cross-object formula fields can reference fields from up to 10 levels away.
* A lookup relationship can be changes to master-detail relationship only if all records have a value in the lookup field.
* A user from the same department who is not necessarily another user's manager could have a higher role in the role hierarchy.  If `Grant Access Using Hierarchies` checkbox is selected, that user with the higher role in the role hierarchy would be able to see the performance review even if he is not that person's manager.
Manager group sharing needs to be enabled on the Sharing Settings page.  Once selected, it can be used in manual sharing, sharing rules, and apex managed sharing.  Manager group sharing allows sharing with either the direct and indirect managers or direct and indirect reports of users.  
The `Grant Access Using Hierarchies` checkbox should be deselected to ensure that the records are not shared throughout the role hierarchy.
* Business processes should be created before the creation of record types.
* When the sharing model is defined as private, users will only see the data to which they have access, as well as those below them in the Role Hierarchy if it is enabled.  They will not be able to see the data that their colleagues can see if they share the same role.
## Cases
* If a case does not meet any assignment criteria, it is assigned to the default case owner which can be a user or a queue.

## Field Dependency
* Only a custom picklist or multi-select picklist can be a dependent field in a field dependency.

## Field Validation
* System Validation includes checking for Required Fields, Unique fields and data type.
* System Validation is performed before custom validation rules.

## FLS
* FLS does not override universally required fields.

## Groups
* records cannot be added to groups that allow customers

## Lightning Sync
Lightning Sync cannot be used with Outlook Integration to delete synced contacts automatically in both calendar applications.  Private events can be synced, and synced events can be deleted in both Salesforce and Outlook automatically.  Repeating events created in Salesforce Classic, called recurring events, cannot be synced.  Repeating events in Lightning Experience, called event series, can be synced by enabling the `Sync Event Series` setting.

## List View

## Lookup Filters
In LE, all lookup filters are required, even if admins specify them as optional in Setup.

## Opportunity Team
Each user can define a default Opportunity Team in their personal settings.  The opportunity owner or someone above the owner in the hierarchy can add the opportunity owner's default Opportunity Team by clicking `Add Default Team` on the Opportunity Team related list in Lightning Experience, Salesforce Class, or the Salesforce App.

## Path
It can be created on many standard objects in Lightning Experience only. 
* A Path can be based on any existing piclist field on the object.  
* After the Path is created, it must be placed on the page like any other Lightning Component.

## Queues
* Only members of a queue can accept records from that queue and take ownership.  
* Queues can be created for standard objects
* Queues can be created for custom objects
* List views are automatically created when a queue is created.
* Records can be placed in a queue manually by a user, but more often an assignment rule is created to automate the process based on criteria.

## Record Types
* Allow you to define picklist values, Paths, and page layouts.
* Record Types can be assigned to profiles but they do not control profiles or approval processes.
* RT cannot be used to display different apps to users.  
* RT cannot have criteria to make different records visible to users.

## Sharing Settings
### User Visibility Settings
* Community User Visibility - If enabled, community users in the same community can see each other, regardless of the organization-wide defaults.  If Portal User Visibility is also selected, portal users can see other portal users from the same account.
### Other Sharing Settings
* `Standard Report Visibility` - If enabled, users can view reports based on standard report types that may expose data of users to whom they dont have access, regardless of the organization-wide defaults.
* `Manual User Record Sharing` - If enabled, users can share their own user record.
* `Manager Groups` - If enabled, users can share records with their managers and manager subordinates groups.
* `Use person role for first user in Community account` - Assign person roles to new community users in accounts without existing users.  This setting also applies to High Volume Customer Portal users who upgrade to Customer Community Plus of Partner Community licenses.  If this setting is disabled, portal roles are created for new users.  
* `Grant community users access to related cases` - Users with Customer Community Plus licenses can view and edit cases in which they are listed as the contact.  
##
* Work orders can be associated with Accounts, Assets, Cases, Contacts, Entitlements, Service Cotracts, other Work Orders, standard and custom objects with custom relationships, knowledge articles and work order line items.  
    * Knowledge articles can be attached and detached from a `Work Order` or `Work Order Line Item`.  They can be viewed but not updated in the Salesforce App.  The `Knowledge One Widget` is used to search for articles.
* Use Process Builder with a flow action to convert the lead and add a `Wait` element to set a one day wait period to automatically email the contact. The `Wait` element can automate processes that require a time-based waiting period.  A `Wait` element can be added to a flow and configured for events it needs to wait for.
* `News` feature is available on accounts, contacts, leads, and the Home Page.
* Permission sets may be specified that delegated administrators can assign to users in specified roles and all subordinate roles.

## Validation Rules
* `PRIORVALUE` function can be used to prevent further changes to a record when the value of the Status field on the record is set to a specified value.
* `ISCHANGED` function would only check whether the value of the Status field is changed.
* Access to a Record can be removed using Process Builder and Flow.
* PB and Flow can be used to grant additional access to a user group using a Share Object based on custom criteria.  

## Sales and Marketing Applications
1. Custom fields in the Lead object can be mapped to what two types of fields?
    * Custom opportunity
    * Custom account
2. Create a page layout, sales process, and record type for each type of sale.
3. Create opportunity update reminders.
4. What two objects can be related to campaign members?
    * Leads and Contacts
5. How can multiple Campaign records be associated with a single opportunity?
      * Campaign Influence
6. What feature tracks how often a file is viewed?
      * Content Deliveries
7. What two related lists should be added to the opp page layout to track how campaigns contribute to the overall pipeline?
      * Campaign Influence and Contact Roles
## Prep for Service and Support Applications
1. Configuration action should be performed to ensure every case gets assigned to a valid owner?
   * Define the `Default Case Owner` in `Support Settings`
2. What is a potential benefit of using Suggested Solutions?
    * Reduced support costs

## Mobile Administration
1. What option can be added to Outlook Publisher Layouts?
    * Quick Actions
2. Lightning for Outlook
    * Link emails in MS Outlook to contacts, leads, accounts, opportunities and cases in Salesforce. 
    * Relate events to records within Salesforce.

## Control Access to Records
### Record-Level Security
* The permissions on a record are always evaluated according to a combination of object-level, field-level, and record-level permissions.
* When object-level permissions conflict with record-level permissions, the most restrictive settings win.

* Org-wide defaults specify the default level of access users have to each other’s records.
* Role hierarchies ensure managers have access to the same records as their subordinates. Each role in the hierarchy represents a level of data access that a user or group of users needs.
* Sharing rules are automatic exceptions to org-wide defaults for particular groups of users, to give them access to records they don’t own or can’t normally see.
* Manual sharing lets record owners give read and edit permissions to users who might not have access to the record any other way.
*  a detail record automatically inherits the sharing setting of its parent
* By default, a role hierarchy automatically grants access to records for users above the record owner in the hierarchy. 

## Define Sharing Rules 
* sharing rules can never be stricter than your org-wide default settings. They just allow greater access for particular users.
Each sharing rule has three components:
   * Share which records?
   * With which users? 
   * What kind of access? - You can assign either Read-Only or Read/Write access.
   
Before creating a sharing rule, it’s important to set up the appropriate public group. A public group is a collection of individual users, other groups, individual roles or territories, and/or roles or territories with their subordinates that all have a function in common.

## Standard and Custom Objects
Types of fields that can be controlling field in a field dependency:
* Standard Checkbox
* Custom Checkbox
* Standard Picklist
* Custom Picklist

* Formula fields are the preferred choice when child record fields need to be populated with the parent record field information.
* Cross-object formula fields can reference fields from up to 10 levels away.
* A lookup relationship can be changes to master-detail relationship only if all records have a value in the lookup field.
* A user from the same department who is not necessarily another user's manager could have a higher role in the role hierarchy.  If `Grant Access Using Hierarchies` checkbox is selected, that user with the higher role in the role hierarchy would be able to see the performance review even if he is not that person's manager.
Manager group sharing needs to be enabled on the Sharing Settings page.  Once selected, it can be used in manual sharing, sharing rules, and apex managed sharing.  Manager group sharing allows sharing with either the direct and indirect managers or direct and indirect reports of users.  
The `Grant Access Using Hierarchies` checkbox should be deselected to ensure that the records are not shared throughout the role hierarchy.
* Business processes should be created before the creation of record types.

## Bulk Macros
* Bulk Macros can run on multiple records from Accounts, Cases, Contacts and Lead objects.  
* Bulk macros can run on records in one object list view at a time.  
* Bulk macros can send emails or update multiple values for multiple records.

## Cases
* If a case does not meet any assignment criteria, it is assigned to the default case owner which can be a user or a queue.

## Field Dependency
* Only a custom picklist or multi-select picklist can be a dependent field in a field dependency.

## Field Validation
* System Validation includes checking for Required Fields, Unique fields and data type.
* System Validation is performed before custom validation rules.

## FLS
* FLS does not override universally required fields.

## Groups
* records cannot be added to groups that allow customers

## Lightning Sync
Lightning Sync cannot be used with Outlook Integration to delete synced contacts automatically in both calendar applications.  Private events can be synced, and synced events can be deleted in both Salesforce and Outlook automatically.  Repeating events created in Salesforce Classic, called recurring events, cannot be synced.  Repeating events in Lightning Experience, called event series, can be synced by enabling the `Sync Event Series` setting.

## List View

## Lookup Filters
In LE, all lookup filters are required, even if admins specify them as optional in Setup.

## Opportunity Team
Each user can define a default Opportunity Team in their personal settings.  The opportunity owner or someone above the owner in the hierarchy can add the opportunity owner's default Opportunity Team by clicking `Add Default Team` on the Opportunity Team related list in Lightning Experience, Salesforce Class, or the Salesforce App.

## Path
It can be created on many standard objects in Lightning Experience only. 
* A Path can be based on any existing piclist field on the object.  
* After the Path is created, it must be placed on the page like any other Lightning Component.

## Profiles
Profile Object settings include:
* Tab settings
* Record types and page layout settings
* Object permissions
* Field permissions

## Queues
* Only members of a queue can accept records from that queue and take ownership.  
* Queues can be created for standard objects
* Queues can be created for custom objects
* List views are automatically created when a queue is created.
* Records can be placed in a queue manually by a user, but more often an assignment rule is created to automate the process based on criteria.

## Record Types
* Allow you to define picklist values, Paths, and page layouts.
* Record Types can be assigned to profiles but they do not control profiles or approval processes.
* RT cannot be used to display different apps to users.  
* RT cannot have criteria to make different records visible to users.

## Role Hierarchy
* RH grants access to data according to the hierarchy and does not work across all levels.  
* Sharing rules can be added to grant access to users at same levels.  The sharing rule would be based on the record owner and share records owned by one role with users of another role.

## Sharing Settings
### User Visibility Settings
* Community User Visibility - If enabled, community users in the same community can see each other, regardless of the organization-wide defaults.  If Portal User Visibility is also selected, portal users can see other portal users from the same account.
### Other Sharing Settings
* `Standard Report Visibility` - If enabled, users can view reports based on standard report types that may expose data of users to whom they dont have access, regardless of the organization-wide defaults.
* `Manual User Record Sharing` - If enabled, users can share their own user record.
* `Manager Groups` - If enabled, users can share records with their managers and manager subordinates groups.
* `Use person role for first user in Community account` - Assign person roles to new community users in accounts without existing users.  This setting also applies to High Volume Customer Portal users who upgrade to Customer Community Plus of Partner Community licenses.  If this setting is disabled, portal roles are created for new users.  
* `Grant community users access to related cases` - Users with Customer Community Plus licenses can view and edit cases in which they are listed as the contact.  
##
* Work orders can be associated with Accounts, Assets, Cases, Contacts, Entitlements, Service Cotracts, other Work Orders, standard and custom objects with custom relationships, knowledge articles and work order line items.  
    * Knowledge articles can be attached and detached from a `Work Order` or `Work Order Line Item`.  They can be viewed but not updated in the Salesforce App.  The `Knowledge One Widget` is used to search for articles.
* Use Process Builder with a flow action to convert the lead and add a `Wait` element to set a one day wait period to automatically email the contact. The `Wait` element can automate processes that require a time-based waiting period.  A `Wait` element can be added to a flow and configured for events it needs to wait for.
* `News` feature is available on accounts, contacts, leads, and the Home Page.
* Permission sets may be specified that delegated administrators can assign to users in specified roles and all subordinate roles.

## Validation Rules
* `PRIORVALUE` function can be used to prevent further changes to a record when the value of the Status field on the record is set to a specified value.
* `ISCHANGED` function would only check whether the value of the Status field is changed.
* Access to a Record can be removed using Process Builder and Flow.
* PB and Flow can be used to grant additional access to a user group using a Share Object based on custom criteria.  

## Sales and Marketing Applications
* The Automated Account Fields feature is only available in Lightning Experience.  It displays US - based companies in the Account Name field as users enter information.  Users can select a suggested company from the list, making it easier to create new business accounts.  When a company is selected from a list, multiple fields are automatically filled.
* Custom fields on the Lead object cannot be mapped on the Opportunity object, but they can be mapped to other custom fields.  A workflow filed update can be used to update the standard Description field on Opportunity records from the mapped custom field.
* A formula field cannot use a custom field's value from a converted lead.  
* A flow cannot be triggered automatically when a lead is converted.
* Validation rule: Please provide at least phone number of email address: `if ( SuupliedPhone = NULL && SuppliedEmail = NULL, True, False)`
