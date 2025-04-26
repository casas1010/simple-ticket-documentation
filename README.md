
# Table of Contents

1. [Introduction](#introduction)  
2. [What is SimpleTicket?](#what-is-simpleticket)  
3. [User Interfaces](#user-interfaces)  
   - [Side Navigator](#side-navigator)  
   - [Record List](#record-list)  
   - [Form View](#form-view)  
4. [Views](#views)  
5. [View rules & User preferences](#view-rules-and-user-preference)  
   - [Logic gates](#side-navigator)  
   - [View rule configuration](#view-rule-configuration)  
6. [Columns](#columns)
7. [Buttons](#buttons)
   - [Properties](#properties)
   - [Server side](#server-side)  
   - [Client side](#client-side)  
8. [Client side script](#client-side-script)
9. [Server side script](#server-side-script)
10. [Side navigator](#side-navigatior-config)  
11. [Access control](#access-control)  
12. [Notification](#notification)  

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

>![SimpleTicket UI](https://i.imgur.com/6rqLxPw.png)
- **Display/hide submenu**: Toggles visibility of user logic such as user profile or logout. If you are an admin, you will see the dev menu that contains the current scope and the saved configuration bucket where changes will be saved. (More on these topics later)
- **Hide/display navigator**: Toggles the side navigator visibility.

---

### Record list

![SimpleTicket UI](https://i.imgur.com/7G8FNIJ.png)
- **Display/hide filter**: Toggles visibility of the filter panel.
- **Filter**: Allows the user to input search parameters.
- **Configure columns**: Controls the column order.  
    > ![SimpleTicket UI](https://i.imgur.com/8YnTbVy.png)
  - **Update user preference**: Controls the column order for the currently logged-in user.  
  - **Update view**: Controls the column order for the view.
- **Search box**: Used to search through the modules and applications available to the user.
- **Menu application**: Container for modules.
- **Menu module**: Contains navigation functionality to list/form/board.
- **Button bar**: Displays buttons/actions the user can perform.
- **Column search**: Entering search criteria creates an AND condition in the filter.
- **Column sort toggle**: Clicking a column header sorts data by that column.
    > ![SimpleTicket UI](https://i.imgur.com/dEVAeDf.png)
- **Record count**: Displays the total number of records per filter, as well as the current page in relation to the total number of records.
- **Record preview**: Allows the user to preview the record.
    > ![SimpleTicket UI](https://i.imgur.com/lsolCPo.png)
- **Buttons**: Additional buttons appear when right-clicking on the button bar, column header, or record. All these buttons are configurable.
    > ![SimpleTicket UI](https://i.imgur.com/CzRGnED.png)

---

### Form view
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
---

### Views
> Views define how form and list layouts are presented, controlling the order and visibility of fields and columns.
This is how views/sections/columns/related-lists relate
> ![SimpleTicket UI](https://i.imgur.com/vvQdkUD.png)

---

### View rules & User preferences
#### Logic gates
> Used to control which form view a user sees when they view a record list or open a record.
> The logic for which rule to apply is described in the diagram below
> ![SimpleTicket UI](https://i.imgur.com/UMyDOtE.png)
#### View rule configuration
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


