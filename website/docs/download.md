---
layout: article
title: Download
aside:
  toc: true
permalink: /download/
---
## Current Beta Version
### 3.0.0.1

**Released**
: TBD

**Fixed**
: * Application trees in an [AppTree]({% link docs/reference/actionelements.md %}#apptree) interactive action no longer scroll to the bottom initially.
* Fonts for [InputCheckbox]({% link docs/reference/allelements.md %}#inputcheckbox) field types on [Input]({% link docs/reference/actionelements.md %}#input) interactive actions are now shown properly.
* Task sequence variable names for all actions corrected to proprly allow for dashes and follow the rules listsed in the [Custom variables](https://docs.microsoft.com/en-us/mem/configmgr/osd/understand/using-task-sequence-variables#bkmk_custom) official documentation.
* The tree control in an [AppTree]({% link docs/reference/actionelements.md %}#apptree) interactive action is now set as initially focused.

**Added**
: * Successful authentication using a [UserAuth]({% link docs/reference/actionelements.md %}#userauth) dialog action now also populates the display name for the authenticated user in the **XAuthenticatedUserDisplayName** variable.
* **NoDefaultButton** attribute for [AppTree]({% link docs/reference/actionelements.md %}#apptree) and [Input]({% link docs/reference/actionelements.md %}#input) interactive actions. This prevents pressing the Enter key from dismissing the dialog if a button does not have focus.

## Previous Beta Versions
### 3.0.0.0 

[Download](https://home.memftw.com/download/7151/?version=3-0-0-0){: .button--info.button--pill}

**Released**
: 7 June, 2020

**Added**
: * Ability to specify a domain controller to use for a [UserAuth]({% link docs/reference/actionelements.md %}#userauth) dialog action using a new [DomainController]({% link docs/reference/actionelements.md %}#userauth) attribute.
* Ability to specify a font for all UI++ elements using the [Font]({% link docs/reference/allelements.md %}#uipp) attribute.
* Two new values to the [DefaultValues]({% link docs/reference/defaultvalues.md %}) action for the [Asset]({% link docs/reference/defaultvalues.md %}#asset) category: *XSystemDiskTotalSizeGB* and *XSystemDiskFreespaceGB*.
* `Preview`{:.warning} [InfoFullScreen]({% link docs/actionconfig/infofullscreen.md %}) actions which create full-screen windows with an informational message.
* **ReadOnly** attribute to the [InputText]({% link docs/reference/allelements.md %}#inputtext) field type on [Input]({% link docs/reference/actionelements.md %}#input) interactive actions.
* **CenterTitle** attribute to the [AppTree]({% link docs/reference/actionelements.md %}#apptree), [ErrorInfo]({% link docs/reference/actionelements.md %}#errorinfo), [Info]({% link docs/reference/actionelements.md %}#info), [Input]({% link docs/reference/actionelements.md %}#input), and [Preflight]({% link docs/reference/actionelements.md %}#preflight) interactive dialog actions.
* [RandomString]({% link docs/actionconfig/randomstring.md %}) non-interactive action to generate a random string of characters.
* **ShowCancel** attribute to the [ErrorInfo]({% link docs/reference/actionelements.md %}#errorinfo) interactive dialog action to prevent exiting UI++ during WinPE when UI++ shows this action.
* New **TimeoutAction** value, **ContinueNoPreempt**, to the [Info]({% link docs/reference/actionelements.md %}#info) interactive dialog action to prevent users from dismissing this action. UI++ automatically dismisses the action when the timeout is reached.
* [Status Message]({% link docs/configuration/statusmessages.md %}) customization.


**Updated**
: * Even more bugs that resulted in a crash when including User values in a **DefaultValues** action.
 * Default UI++ font is now Tahoma which is included in WinPE 5.0 and above.
 * Dynamic font sizing to accomodate longer text string for [Interactive action]({% link docs/actions/interactiveactions.md %}) dialog titles, status messages, and **InputText** items within [Input]({% link docs/reference/actionelements.md %}#input) interactive actions.
 * Changed the name of the **TextInput**, **ChoiceInput**, **CheckboxInput** elements to **InputText**, **InputChoice**, and **InputCheckbox** for consistency. The old names are now deprecated but will work. Strongly consider changing all configuration files to use the new names.
 * [Active Directory Checks]({% link docs/configuration/activedirectorychecks.md %}) now include warnings and user name validation.
 * Modified the wired LAN connection detection that is part of the [DefaultValues]({% link docs/reference/defaultvalues.md %}) action to not depend on localizable text in the Win32_NetworkAdapater WMI class's **AdapterType** property. **XWiredLANConnected** is now also set to *False* when no wired adapters are found at all.
 * The [AppTree]({% link docs/reference/actionelements.md %}#apptree) interactive action always creates one additional variable in the application and package variable lists with a blank value. This handles cases where the user returns to the **AppTree** and modifies the selected items so that fewer items are now selected.
 * Update the internal XML parser, [pugixml](https://pugixml.org/), to version 1.10.


## Current Production Version
### 2.11.1.2 

[Download](https://home.memftw.com/download/7151/?version=2-11-1-2){: .button--info.button--pill}

**Released**
: 21 April, 2019

**Fixed**
: * Additional bugs that resulted in a crash when including User values in a **DefaultValues** action.
 * WMIRead action not working at all.
 * **DefaultValues** action now always hides the task sequence progress bar if the **DefaultValues** action shows its own progress bar.

## Previous Stable Versions
### 2.11.1.1 

[Download](https://home.memftw.com/download/7151/?version=2-11-1-1){: .button--warning.button--pill}

**Released**
: 28 February, 2019

**Fixed**
: * Additional bug that resulted in a crash when including User values in a **DefaultValues** action.
 * Domain name field in **UserAuth** action set to read-only is now actually read-only.
 * Bug that resulted in a crash when specifying the Tall Size for a **Preflight** action.
 * Bug that resulted in a crash when clicking in open space on an AppTree action.
 * Bug that resulted in a crash when including User values in a **DefaultValues** action.

**Updated**
: * Separated logging functionality to its own DLL. Ensure that you now also include the FTWCMLog.dll file in any boot media, packages, or locations that you run UI++ from.
 * **UserAuth** actions now look for the closest domain controller to connect to.

### 2.11.0.3 

[Download](https://home.memftw.com/download/7151/?version=2-11-0-3){: .button--warning.button--pill}

**Info**
: * Released: 7 December, 2018
 * Zip download file hash (SHA256): 0882B506BAB9AE6051909B6FFC190D3751FB786EFC80D6D6B3F6D8CE0ED70649
 * UI++.exe file hash (SHA256): D4DE8D87709B4F92ABEDCA73ADCCC1DF5F41DFB822A4DA5289A90B718F2A3920
 * UI++64.exe file hash (SHA256): 08BCD93DAAB6EDE443B03878BDC5651E3A5F6BD5DD96658079FCD81BC652E25B

**Fixed**
: * Overlapping time countdown and next/OK button on a **Preflight** action dialog when all four buttons are shown.
 * Scaling of text on an **InputInfo** item properly accounts for two-line **InputInfo**
 * Visual C++ Runtime library .dll dependency.
 * An issue where XHWChassisType was not set properly for virtual machines.
 * Random text color for **InputText** items.

**Added**
: * Lenovo model detection during a **DefaultValues** action.
 * Optional removal of the sidebar from dialogs.
 * Active Directory computer name check.
 * The **Preflight** action can now display warnings in addition to failures.
 * The **Preflight** action can now have a countdown exactly like the **Info** action.
 * A refresh button to the **Preflight** action.
 * Horizontal scroll option on **InputText** elements.

**Updated**
: * Separated LDAP functionality into its own DLL. Ensure that you now also include the FTWldap.dll file in any boot media, packages, or locations that you run UI++ from.
 * The dialog border color now matches the Color value set on the UIpp root element.
 * Flat dialogs now have a border.
 * The countdown timer for **Info** actions now appears to the right of the dialog buttons and includes only the time remaining.
 * The countdown timer changes color to orange when 25% of the time remains and red when 10% remains.
 * The **DefaultValues** action now recognizes ChassisTypes with code 35 and 36 as desktops.
 * Tooltips for **Preflight** check descriptions are now displayed using an info icon displayed before the item instead of on the text itself.

**Removed**
: * Customization or inclusion of a timer countdown message on the **Info** action.
 * Dialog Icons.

### 2.10.4.0 

[Download](https://home.memftw.com/download/7151/?version=2-10-4-0){: .button--warning.button--pill}

**Info**
: * Released: 24 May, 2018
 * Zip download file hash (SHA256): A04C4A0EEC53424C40290BADB90515E6D0AE4E692765E5350D63FBB0311F9523
 * UI++.exe file hash (SHA256): 45056B10A056002B2BA4515B279EE2DEEF2E89A628BD6F3FE840E04A99A186C3
 * UI++64.exe file hash (SHA256): 2983AED3126895BE218E80A77C2E14728F7D33F7AE1DD1F359BC37FF9C9DC1E7

**Updated**
: * Regular Expression matches on **Case** elements within a **Switch** action now match on substrings instead of just the complete string specified in the **OnValue** attribute.
 * Reverted variable substitution behavior so that if a variable is not found, it is replaced by a blank value.
 * Variable substitution now replaces variables with environment variable values as well as task sequence variable values.
Environment variable values take precedence in cases of name collisions.
 * **DefaultValues** action determination of the XSystemUEFI variable’s value now matches what ConfigMgr does for _SMSTSBootUEFI.
 * **InputInfo** elements within a **UserInput** action now scale their font size based on the line length to accommodate longer strings.
 * The list box portion of an **InputChoice** now dynamically increases its width to show longer choices.
 * The edit box portion of an **InputChoice** now displays a tooltip if the user hovers over it and the choice selected is too long.

**Fixed**
: * **UserAuth** action with the **GetGroups** attribute set to True successfully checked authentication but did not allow progress to the next action.
 * Condition evaluation bug where in some cases conditions based on single variable values did not correctly return True.