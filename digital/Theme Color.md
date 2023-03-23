
# **System Theme Color**

The system theme color feature allows users to customize the background color of their phone by switching between light mode and dark mode.

## **The idea behind**

By default, the theme is set to light mode, but users have the option to switch to dark mode at any time. It is assumed that users who customize their settings are more technically adept and pay more attention to the applications they install on their phone.

## **Methodology**

You need to gather user_propertie_theme from your app SDK.

### **Data source**

Any event tracking system, e.g. amplitude, bigquery, adjust, appslyfer, etc.

### **SQL code**
``` sql
select user_id, user_properties_system_theme as theme
from (
	select user_id, user_properties_system_theme, row_number() over (partition by user_id order by event_time asc) as seqnum
	from your_database.your_dataset 
	where true 
		and user_id is not null
		and user_properties_system_theme is not null
) t1
where t1.seqnum = 1
```

## **Feature performance**
<img width="313" alt="Screenshot 2023-03-15 at 13 13 46" src="https://user-images.githubusercontent.com/120475714/225306065-04ed9e8a-ec50-4346-a1c4-73fbefcaef2a.png">
<img width="333" alt="Screenshot 2023-03-16 at 14 10 36" src="https://user-images.githubusercontent.com/120475714/225627049-3d9cb210-741f-40da-89f6-c6cbdcd98f2e.png">

Validated with SHAP Values


## **Additional Info**
