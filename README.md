
# Table of Contents

1. [Introduction](#introduction)  
2. [What is SimpleTicket?](#what-is-simpleticket)  
3. [User Interfaces](#user-interfaces)  
   - [Side Navigator](#side-navigator)  
   - [Record List](#record-list)  
   - [Form](#form)
4. [Views](#views)  
5. [View rules & User preferences](#view-rules--user-preferences)  
   - [Logic gates](#logic-gates)  
   - [View rule configuration](#view-rule-configuration)  
6. [Columns](#columns)
7. [Buttons](#buttons)
   - [Properties](#properties)
   - [Location](#location)
   - [Script](#script)
   - [Server side](#server-side)  
   - [Client side](#client-side)  
8. [Client script](#client-script-sys_client_script)
9. [Client side APIs](#client-side-apis)
10. [Server rules](#server-rules-sys_server_rule)
11. [Server script](#server-script-sys_server_script)
12. [Server side APIs](#server-side-apis)
13. [Side navigator](#side-navigator-1)
14. [Security](#security)  
15. [Notifications](#notifications)
16. [System properties](#system-properties)
17. [Schedule jobs](#schedule-jobs)
18. [Config & Config entry](#config--config-entry)
19. [Import config & its entries](#import-config--its-entries)
20. [Reports](#reports)
21. [Report Board](#report-board)
22. [Virtual view/table](#virtual-viewtable)
---

## Introduction

> Welcome to the SimpleTicket Developer Manual. This guide is designed for new and experienced developers alike to help understand, build, and optimize applications on the SimpleTicket platform.

---

## What is SimpleTicket?

> SimpleTicket is a cloud-based platform offering digital workflows that create great experiences and unlock productivity. It's widely used for Sales Management, IT Operations, HR, Security, and Customer Service workflows.

> SimpleTicket is built on a multi-instance architecture and uses a single-tenant model for security and isolation.  
Everything in SimpleTicket is stored in tables. A **record** is a row in a table, and a **field** is a column.

---

## User interfaces

### Side navigator

> ![SimpleTicket UI](https://i.imgur.com/6rqLxPw.png)
- **Display/hide submenu**: Toggles visibility of user logic such as user profile or logout. If you are an admin, you will see the dev menu that contains the current scope and the saved configuration bucket where changes will be saved. (More on these topics later)
- **Hide/display navigator**: Toggles the side navigator visibility.

---

### Record List

> ![SimpleTicket UI](https://i.imgur.com/7G8FNIJ.png)

- **Display/Hide Filter**: Toggles the visibility of the filter panel.
- **Filter**: Allows users to input search parameters.
- **Configure Columns**: Manages the column order.
  > ![SimpleTicket UI](https://i.imgur.com/8YnTbVy.png)
  - **Update User Preferences**: Sets the column order for the currently logged-in user.
  - **Update View**: Adjusts the column order for the current view.
- **Search Box**: Enables searching across available modules and applications.
- **Menu Application**: Contains modules.
- **Menu Module**: Provides navigation functionality to list, form, or board.
- **Button Bar**: Displays available actions and buttons for the user.
- **Column Search**: Inputting search criteria creates an AND condition for filtering.
- **Column Sort Toggle**: Clicking a column header sorts the data by that column.
  > ![SimpleTicket UI](https://i.imgur.com/dEVAeDf.png)
- **Record Count**: Displays the total number of records that match the filter and indicates the current page relative to the total records.
- **Record Preview**: Allows users to preview a selected record.
  > ![SimpleTicket UI](https://i.imgur.com/lsolCPo.png)
- **Additional Buttons**: Right-clicking on the button bar, column header, or a record reveals configurable buttons.
  > ![SimpleTicket UI](https://i.imgur.com/CzRGnED.png)

---

### Form
> ![SimpleTicket UI](https://i.imgur.com/rKXgZ3V.png)
- **Button bar**: Displays buttons/actions the user can perform.
- **Related list**: Contains a list of related records.
- **Configure columns**: Modify the layout of the form.
    > ![SimpleTicket UI](https://i.imgur.com/hk6BYro.png)
    - **View**: Select the view to configure.  
    - **Number of columns**: Controls whether the section has 1 or 2 columns.  
    - **Section name**: The name of the section.  
    - **Selected columns**: Columns currently displayed in the section.  
    - **Available columns**: Columns available to be added to the section.
    - **Configure attachments**
        > ![SimpleTicket UI](https://i.imgur.com/QAPTPlW.png)    
        - **Download attachment**: Download attachment.  
        - **Remove attachment**: Remove attachment.  
        - **Add attachment**: Add attachment.




## Views
> Views define how form and list layouts are presented, controlling the order and visibility of fields and columns.
This is how views/sections/columns/related-lists relate
> ![SimpleTicket UI](https://i.imgur.com/vvQdkUD.png)

---

## View rules & User preferences
### Logic gates
> Used to control which form view a user sees when they view a record list or open a record.
> The logic for which rule to apply is described in the diagram below
> ![SimpleTicket UI](https://i.imgur.com/UMyDOtE.png)
### View rule configuration
- If sys_type = 'simple', and the sys_filter condition evaluates to true or is null, then the view in sys_view_name is used.
- If sys_type = 'script', and the script is evaluated and whatever string it returns is the view name used.
> ![SimpleTicket UI](https://i.imgur.com/7abGJFF.png)

---



## Columns
- **access_control_table_column**: Used for setting access controls.
    > ![SimpleTicket UI](https://i.imgur.com/bFF6RmK.png)
    - **Table**: Used to pick any table (including virtual)
    - **Restriction**: Used to pick a element(s) to set the access control against. it possible choices are *, all, or a specific column.
        - if * is selected, the access control is applied at a record level.
        - if all is selected, the access control is applied at a table level.
        - if a column is selected, the access controls is applied at a column level.
- **any_record**: Used to pick any record from any table
    > ![SimpleTicket UI](https://i.imgur.com/eFAzu64.png)
- **boolean**: True or false
    > ![SimpleTicket UI](https://i.imgur.com/VQpJZOs.png)

- **date_year_month_day**: Allows the user to select a year-month-day.
    > ![SimpleTicket UI](https://i.imgur.com/yniEGqo.png)
- **date_year_month_day_hour_minute**: Allows the user to select a year-month-day-hour-minute.
    > ![SimpleTicket UI](https://i.imgur.com/rcK80yj.png)
- **date_year_month_day_hour_minute_second**: Allows the user to select a year-month-day-hour-minute-second.
    > ![SimpleTicket UI](https://i.imgur.com/6RrrL6O.png)
- **dropdown**: Allows the user to select a choice from the dropdown.
    > ![SimpleTicket UI](https://i.imgur.com/fycizFk.png)
- **float**: Allows the user to input numbers with decimals.
    > ![SimpleTicket UI](https://i.imgur.com/7kQdEon.png)
- **image**: Allows the user to input a image to display.
    > ![SimpleTicket UI](https://i.imgur.com/KE3atkj.png)
- **int**: Allows the user to input whole numbers.
    > ![SimpleTicket UI](https://i.imgur.com/59bSF85.png)
- **json**: Allows the user to save jsons.
- **long_blob**: Allows the user to store attachments.
- **long_text**: Allows the user to store long texts.
    > ![SimpleTicket UI](https://i.imgur.com/sAT4Llz.png)
- **reference**: Allows the user to select a record from a table.
    > ![SimpleTicket UI](https://i.imgur.com/eFAzu64.png)
- **reference_list**: Allows the user to select multiple records from a table.
    > ![SimpleTicket UI](https://i.imgur.com/MgtF0Y2.png)

- **rich_text**: Allows the user to create rich notifications with html/css.
    > ![SimpleTicket UI](https://i.imgur.com/uD4l8uL.png)
- **script**: Allows the user to script.
    > ![SimpleTicket UI](https://i.imgur.com/BAxIWCD.png)
- **table**: Allows the user to pick any table (including virtual) in the instance.
    > ![SimpleTicket UI](https://i.imgur.com/bQN1v1t.png)
- **table_filter**: Allows the user to create filters for sql record list query.
    > ![SimpleTicket UI](https://i.imgur.com/AidPREX.png)
- **text**: Allows the user to input text
    > ![SimpleTicket UI](https://i.imgur.com/F04oQPB.png)
- **time_day_hour_minute**: Allows the user to input a day( 1 through 31), hour (1 through 24), minute ( 1 through 60)
    > ![SimpleTicket UI](https://i.imgur.com/UsGlyOh.png)

- **time_day_hour_minute_second**: Allows the user to input a day( 1 through 31), hour (1 through 24), minute ( 1 through 60), second (1 through 60)
    > ![SimpleTicket UI](https://i.imgur.com/v7A4j3m.png)
- **time_hour_minute**: Allows the user to input a hour (1 through 24), minute ( 1 through 60)
    > ![SimpleTicket UI](https://i.imgur.com/lrDLU9I.png)

## Buttons
> Buttons are the tool we use to drive actions in the platform. We can describe the button with three high level domains, its properties, location, and script.
### Properties
> ![SimpleTicket UI](https://i.imgur.com/vF2hnlS.png)
- **Button name[sys_button_name]**: Button identifier that can be used to call its script.
- **Name[sys_name]**: Name of the button displayed in the UI.
- **Type[sys_type]**: Describes button apperance.
- **Condition[sys_condition]**: Script that determines whether to display button.
- **Active[sys_active]**: Determines whether to display button.
- **Order[sys_order]**: Determines the buttons position in respect to others.
- **Table[sys_table]**: Determines which table the button will be displayed in.
- **Server[sys_server]**: Determines if the button runs on the client or server side
### Location
> ![SimpleTicket UI](https://i.imgur.com/3yz2F9W.png)
- **Child menu[sys_child_menu_name]**: Determines the parent button if any. this only works with form menu or list menu.
- **Form button[sys_form_button]**: Determines if the button is displayed in the forms button bar.
- **Form menu[sys_form_menu]**: Determines if the button is displayed in the forms button bar menu when the user right clicks on it.
- **Table row[sys_form_menu]**: Determines if the button is displayed when the user right clicks on a record on a record list.
- **List button[sys_list_button]**:Determines if the button is displayed in the record list button bar.
- **Table column header[sys_list_column_header_menu]**: Determines if the button is displayed when the user right clicks on a records list column header.
- **List menu[sys_list_menu]**: Determines if the button is displayed in the list button bar menu when the user right clicks on it.
- **Show on insert[sys_show_on_insert]**: Determines if the button is displayed when the record is new in a form.
- **Show on update[sys_show_on_update]**: Determines if the button is displayed when the record is not new in a form.
### Script
> ![SimpleTicket UI](https://i.imgur.com/5QcqvW4.png)
- **Script[sys_script]**: Contains the set of instructions to run when the user clicks the button
- **Server load script[sys_server_load_script]**: Contains the set of instructions to run when when form is loading on the server. mainly used to get the views.
### Server side
> Server side buttons run on the server side. They can access server side objects.
> Server side buttons can navigate using the nav object. 
```
// ex 1: refresh page:
s.print( 'hello world' );
nav['refresh'] = true;

// ex 2: create a record and navigate to its form to edit it
var created_record = await c.create();
  nav['navIn']={
    'table_name': created_record['sys_table_name'],
    'form_params': {
      'sys_id': created_record['sys_id']
     },
   };

// ex 3: open user list with filter sys_active = true and sys_created_by = juan OR sys_active = true.

nav['navIn'] = {
  'ui_type': 'list',
  'table_name': 'sys_user',
  'list_filter': [
    [
      {
        ""sys_column"": ""sys_active"",
        ""sys_operator"": ""="",
        ""sys_value"": true
      },
      {
        ""sys_column"": ""sys_created_by"",
        ""sys_operator"": ""="",
        ""sys_value"": 'juan'
      }
    ],
    [
      {
        ""sys_column"": ""sys_active"",
        ""sys_operator"": ""="",
        ""sys_value"": false
      }

    ],

  ]
};


ex 4:open facebook in a new tab.

nav['navOut'] = 'www.facebook.com'


```
### Client side
> Client side buttons can on the server and client side or just the client side. 
> Client side buttons can navigate UrlData.
```
// ex: open a form with pre filled values ( sys_active = true ) . To open a new record sys_id = new must be present.
const urlData = new UrlData({
    ui_type: 'form',
    portal_name: 'back',
    table_name: 'sys_user',
    view: 'default_sys_user',
    form_params: { 'sys_id':'new',  'sys_active':true }
});
urlData.setUrl();


// ex: open list with a filter ( sys_active = true AND sys_first_name != 'Tom brady' );
const urlData = new UrlData({
    ui_type: 'list',
    portal_name: 'back',
    table_name: 'sys_user',
    view: 'default_sys_user',
    list_filter: [
        [{ sys_column: 'sys_active', sys_operator: '=', sys_value: 'active' }],
        [{ sys_column: 'sys_first_name', sys_operator: '!=', sys_value:'Tom brady' }]
    ]
});
urlData.setUrl();
```

---

## Client script [sys_client_script]

Scripts that run in the user's browser, typically to manage form behavior, validate data, or dynamically update fields without a full server call. Common examples include:
> ![SimpleTicket UI](https://i.imgur.com/VoIS2K9.png)
- **Name [sys_name]**: Script name
- **Type [sys_type]**: Determines the table column the script should run.
    - **On Change**: Runs when a particular field value changes.
    - **On Load**: Runs when the form loads.
- **UI Type [sys_type]**: Determines the table column the script should run.
- **Table id [sys_table_id1]**: Determines the table where the script should run.
- **Table id [sys_table_id1]**: Determines the column that needs to change in order for the script to run if Type is 'On change'
- **Script [sys_script]**: Instructions executed.

---

## Client side APIs

These scripts enhance user experience by making forms/list interactive and responsive without needing server interaction for every small task.


---

## Server rules [sys_server_rule]
> Scripts that are triggered when a record is inserted, updated, deleted, or queried.
> ![SimpleTicket UI](https://i.imgur.com/HydYuP3.png)
- **Order[sys_order]**: The order of the script.
- **Table[sys_table_id1]**: The order of the script.
- **Filter[sys_filter]**: The sql where equivalent
- **When[sys_when]**: The operation that triggers the script.
- **Read[sys_read]**: Runs when the record is read.
- **Insert[sys_insert]**: Runs when the record is create.
- **Delete[sys_delete]**: Runs when the record is deleted.
- **Condition[sys_condition]**: Condition required to pass in order for the script to run.
- **Script[sys_script]**: Set of instructions to run. it has access to the current(c) and previous(p) states of the record. Script also has access to s.abort(message), it allows you to stop the execution of the action being taken.



---

## Server script [sys_server_script]
> Reusable server-side functions that can be called from other scripts.
> ![SimpleTicket UI](https://i.imgur.com/o4l1IEP.png)
- **Class name[sys_class_name]**: The name of the class to use.
- **Client callable[sys_client_callable]**:The script can be called from the client side.
- **Class name[sys_class_name]**: The name of the class to use.

> Here is a example of how to call a server script from the client side
```
var script_helper = new ServerScriptHelper();
script_helper.class_name = 'UserPreferenceUtils';          // pass class name
script_helper.method_name = 'updateUserPreference';        // pass method name
script_helper.params = {                                   // pass params
    'sys_name': (l.getTable())['sys_name'] + '.list.view',
    'sys_value': v_name['sys_name']
};
var res = await script_helper.get();
```
> To call the script from another server side script just instantiated the class name


## Server-Side APIs

These scripts enhance the user experience by providing access to a variety of different classes and functionalities, enabling seamless interactions and streamlined processes.
---


## Side navigator
> To navigate the app using the side navigator, create a sys_menu_module record.
> ![SimpleTicket UI](https://i.imgur.com/r6oNd5t.png)
- **Link type[sys_link_type]**: Determines the UI to load.
    - Form: A form can be opened to a new record, or to a existing record. we can also pass params throught the url to set as initial values.
        - How to open to a new record:
            - in sys_filter, pass sys_id is new
        - How to open to a existing record:
            - in sys_filter, pass sys_id is xxx
        - How to pass initializing params:
            - in sys_filter, pass the params
    - Record list: A record list can be openend with a filter
    - Board:A board can be openend. Set the table as sys_board and in the sys_filter pass the sys_id of the record to point to.


- **Arguments[sys_arguments]**: Contains additional parameters we can pass such as order by to a record list
- **Table[sys_table_id1]**: Determines which table is being used to load record/records.
- **Table filter[sys_filter]**: 
    - In a record list, it determines which records to display. 
    - In a form, it is used to pass parameters. 
    - In a board, only the sys_id is passed to know which board to open.
- **View name[sys_view_name]**: 
    - In a record list, it determines which view to use.
    - In a form, it determines which view to use.
- **Title[sys_tile]**: Determines the title of the module in the side navigator.
- **Menu id[sys_menu_category_id]**: Determines which menu category to be under.
- **Order[sys_order]**: Determines its position within the menu category.
- **Roles[sys_roles]**: Determines the roles required to see the module.

---

## Security
> ![SimpleTicket UI](https://i.imgur.com/XstdrIT.png)

- **Group**: Defines which user groups have visibility or access to the record or module. 
- **Role**: Specifies the roles required to access or interact with the record.
- **Access controls**: Implemented via Access Control Rules (ACLs) on the table or field level to restrict CRUD (Create, Read, Update, Delete) operations. These rules evaluate conditions, scripts, or roles to grant or deny access.
  > ![SimpleTicket UI](https://i.imgur.com/9ptJ56u.png)
  - **Type [sys_type]**: Determines when the access control is applicable.
  - **Operation [sys_operation]**: Determines whether create/read/update/delete is the action required for the ACL to be applicable.
  - **Table column [sys_table_column_pair]**: Determines the table and restriction that the ACL applies to. See `access_control_table_column` column for more detail.
  - **Table filter [sys_table_filter]**: A filter used to allow the user more granularity for applying the ACL.
  - **Script [sys_script]**: Instructions that determine if the user is allowed access to the record or not. To allow access set `result = true`, to deny set `result = false`.

---

## Notifications
> Notifications allow you to configure automatic emails sent to users or groups based on record changes, events, or conditions.
> Notifications Body and Subject allow you to grab information from the record that triggered it using ${COLUMN_NAME}. for Example if its a the users table that the notification is against, then the subject can be "Hello ${sys_first_name}" and use the users first name. sys_first_name is a column in the sys_user table.
> Notifications can carry attachments two different ways, by adding a download link and by adding the attachment itself to the email.
> ![SimpleTicket UI](https://i.imgur.com/YNI87er.png)
  - **Name [sys_name]**: The name of the notification
  - **Subject [sys_subject]**: The subject of the email
  - **Body [sys_body]**: The body of the email
  - **Action when to send [sys_when]**: Determines when the action that triggers the email being sent (Create, Update, Create or Update, Event triggered)
  - **Table [sys_table]**: The table that contains the trigger to send the email. Only applicable if 'Action when to send' is not 'Event triggered'
  - **Table filter [sys_table_filter]**: A filter to allow more granularity of the record that triggers the notification
  - **Event [sys_event]**: The event name to listen for when 'Action when to send' is set to 'Event triggered'. This event must match a defined event in the system.
  - **Groups [sys_groups]**: One or more user groups that should receive the notification. Members of the selected groups will be notified.
  - **Users [sys_users]**: Individual users who should directly receive the notification.

---



## System properties
> System properties are configurable values that control the behavior and settings of the SimpleTicket platform. They allow administrators to modify features without altering code.
> ![SimpleTicket UI](https://i.imgur.com/HmF7Jmf.png)
- **Name[sys_name]**: Name of the property
- **Description[sys_description]**: Describes what the property is and used for
- **Type[sys_type]**: The type of property (String or Number)
- **Value[sys_value]**: The value of the property

---

## Schedule jobs
> Scheduled jobs automate background tasks and processes, such as running scripts or importing data, at defined times or intervals. 
> ![SimpleTicket UI](https://i.imgur.com/iupM7sh.png)
- **Condition[sys_condition]**: Dictates whether the script runs or not, runs server side.
- **Script[sys_script]**: Set of instructions to run.
> ![SimpleTicket UI](https://i.imgur.com/v4j0wqG.png)
There are 5 types of schedule jobs. here are their configurations:
- **Weekly**: Job runs once a week on the given Day of the week [sys_day_of_week]. it also takes in starting date[sys_starting].
- **Daily**: Job runs daily at the given Time [sys_time] in a 24/7 format.
- **Monthly**: Job runs once a month on the given Day of the month [sys_day_of_month]. it also takes in starting date[sys_starting].
- **Yearly**: Job runs once a year on the given Day of the year [sys_day_of_year]. it also takes in starting date[sys_starting].
- **Once**: Job runs once a on the given One time [sys_one_time].


---



## Config & Config entry
> SimpleTicket mechanism for storing changes dev changes is quite simple. Each table has a sys_track_changes flag, if the flag is set to true and a crud operation occurs, then the change is saved. Config [sys_saved_configuration] is the table that stores where the change record is stored. Config entry [sys_config_entry] is the record that stores the actual change

---

## Import config & its entries
> Import config is used when you want to import data from another SimpleTicket instance into yours without triggering acls/server rules and without writing the record system properties such as sys_created_by. Import configs [sys_imported_saved_configuration] can be though of as a container for keeping changes, Import config entries [sys_imported_saved_configuration_data] is the record that contains the actual change.

---

## Reports
> Reports allow users to visualize, analyze, and share data using various chart types, lists, and dashboards for informed decision-making. If you click in a reports section, it will open a new widown with record list of the given table with the filter
> ![SimpleTicket UI](https://i.imgur.com/UQ21rwc.png)
- **Report UI editor**: Button that opens up report creator UI
> ![SimpleTicket UI](https://i.imgur.com/WFdAaYG.png)
- **Name [sys_title]**: The title of the report.
- **Data input type [sys_input_data_type]**: The table to run the report against.
- **Table [sys_table_id1]**: The table to run the report against
- **Group by [sys_selected_group_by_column]**: The column displayed in the report. It allows dot walking if the column is of reference type
- **Data display type [sys_data_display_type]**: The report style (dount/donut/line)
- **Time count [sys_time_unit]**: The time unit for the x axis in a line report.
- **Query operation [sys_query_operation]**: Determines the method for counting the datas in the report.

---

## Report Board
> Report boards provide a centralized visual display of key metrics, reports, and performance indicators, helping users and teams monitor activity and make data-driven decisions. To create a report board the the type to report, add a name, and click 'Create'.
> ![SimpleTicket UI](https://i.imgur.com/l1BbiNO.png)
> To open the Report board UI click on the Board UI editor as shown below.
> To open the board, click on 'View board'.
> ![SimpleTicket UI](https://i.imgur.com/VCKpM6O.png)

> ![SimpleTicket UI](https://i.imgur.com/JBWSvvP.png)
- **Report picker**: Drag and drop  of available reports
- **Section title**: The title of the section.
- **Report picker**: The title of the board.
- **Remove report**: Remove the report.
- **Add section**: Add a section.

Below is shows how a board would look like
> ![SimpleTicket UI](https://i.imgur.com/YVd6ROM.png)




---

## Virtual view/table
> Virtual views (`sys_virtual_view`) allow you to join tables virtually, without creating new tables or duplicating data. They are useful when you need to report on or query data across multiple related tables. Each virtual view has virtual tables (`sys_virtual_table`) that determine the tables and join style.
> ![SimpleTicket UI](https://i.imgur.com/FSF2om2.png)
- **Name [sys_name]**: The title of the view.
- **Label [sys_label]**: The name shown in the view.
- **Order [sys_order]**: The table's position in the join query.
- **Where clause [sys_where_clause]**: The alias of the table in the join query.
- **Table alias [sys_table_alias]**: The table's alias in the join.
- **Virtual table view [sys_virtual_table_view_id]**: Links to the virtual view.

---