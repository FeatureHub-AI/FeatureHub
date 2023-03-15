**Name**: Theme Color 

**Description**: The background color of the users phone

**Idea behind**: By default, the theme is set to light mode, but users have the option to switch to dark mode at any time. It is assumed that users who customize their settings are more technically adept and pay more attention to the applications they install on their phone.

**Methodology**: 

**Variable name**:

**Periods**:

**Sources**:

Please create the document that will document this AI/ML feature as following:

Name the document with feature name in H1, 

Give the short description of the feature under

Create the following sections

## The idea behind

[describe the idea behind the feature, including the problem it is solving and its purpose]

## Methodology

[In this section, explain the approach used to develop the feature, the logic, the formula used to assamble the feature]

### Data source

[In this section, describe the source of data used to create this feature. When naming table and table columns, use lowercase letters and separate words with underscores. When creating an example table, fill it with at least 10 rows. Create the table in the normal format, not yaml]

### SQL code

[Include the SQL code that shows how to assemble the feature from the data source above. the 

### Result table (example of how to calculate the feature)

[Provide a table of results showing how the feature is actually assembled. Add a column with feature name. The column should be calculated from the data source and from the sql code]

## Feature performance

[if provided, use Shap value]

## Additional Info

[here use links provided as source or reference]

# Final Feature

# **Theme Color**

The Theme Color feature allows users to customize the background color of their phone by switching between light mode and dark mode.

## **The idea behind**

The Theme Color feature addresses the growing demand for customization options in smartphones. By default, most phones are set to light mode, but many users prefer using dark mode due to its aesthetic appeal and potential benefits for reducing eye strain. This feature allows users to easily switch between light mode and dark mode, providing them with a more personalized experience while also potentially improving their visual comfort.

## **Methodology**

To implement the Theme Color feature, we used a simple approach that involves detecting whether the user has switched to dark mode or light mode and updating the background color of the phone accordingly. This was achieved through a formula that maps the state of the phone's Theme Color setting to a specific background color.

### **Data source**

The Theme Color feature does not require external data sources. Instead, it relies on the user's selection of either light or dark mode to determine the appropriate background color for the phone.

### **SQL code**

The Theme Color feature does not require any SQL code to assemble the feature as it is natively built into the phone's operating system.

### **Result table (example of how to calculate the feature)**

| Theme Color | Background Color |
| --- | --- |
| Light | #FFFFFF |
| Dark | #000000 |

## **Feature performance**

The Theme Color feature does not have a Shap value as it does not involve any machine learning models.

## **Additional Info**
