
# **Theme Color**

The theme color feature allows users to customize the background color of their phone by switching between light mode and dark mode.

## **The idea behind**

By default, the theme is set to light mode, but users have the option to switch to dark mode at any time. It is assumed that users who customize their settings are more technically adept and pay more attention to the applications they install on their phone.

## **Methodology**

To implement the theme color feature, we used a simple approach that involves detecting whether the user has switched to dark mode or light mode and updating the background color of the phone accordingly. This was achieved through a formula that maps the state of the phone's theme color setting to a specific background color.

### **Data source**

The theme color feature does not require external data sources. Instead, it relies on the user's selection of either light or dark mode to determine the appropriate background color for the phone.

### **SQL code**

Does not require any SQL code to assemble the feature as it is natively built into the phone's operating system.

### **Result table (example of how to calculate the feature)**

| Theme Color | Background Color |
| --- | --- |
| Light | #FFFFFF |
| Dark | #000000 |

## **Feature performance**
<img width="313" alt="Screenshot 2023-03-15 at 13 13 46" src="https://user-images.githubusercontent.com/120475714/225306065-04ed9e8a-ec50-4346-a1c4-73fbefcaef2a.png">
<img width="333" alt="Screenshot 2023-03-16 at 14 10 36" src="https://user-images.githubusercontent.com/120475714/225627049-3d9cb210-741f-40da-89f6-c6cbdcd98f2e.png">

Validated with SHAP Values


## **Additional Info**
