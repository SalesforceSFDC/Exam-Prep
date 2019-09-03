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
