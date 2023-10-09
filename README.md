# Sales Force

## Important Points
1. Sales Force provides default feature which are called as Standard Objects/Apps
2. Standard Application can be customized to limited 
3. We Need to create Object for which we will be creating the TAB   
4. We need API Name in order to access the Object in Apex Code
5. API Name in all Custom Objects will be appended with ObjectName with 2 Underscore plus C
   - Ex : Student__c
6. Numeric Data Type length is 18 digits including decimal value
7. FLS => Field Level Security
8. max nbr can be added in 1 object
   - 800 (unlimited)
   - 500 (enterprise) 
   - 500 (developer) 
9. you can restored the deleted records within 15 from a recycle bin
   - in app launcher, search for recycle bin 

## Create Application

### FLow
> Create Application
> Create Object using Onject to create a New Tab  or
> Create TAB, you wil an option to create a New Object

### Steps
1. Login
2. Click on the Gear Link
3. Expand App
4. Click on the App Manager
5. Add Details
6. Add Profile to the application
7. 

## Navigate from One Application to App
> App Launcher which is present in the left side of the page

## Create Object
1. Click on Gear
2. Enter Object Manager in Quick Find
3. Click on New Custom Object
4. Enter Details
   > Label = Student (this name is like a table in oracle)
   > Plural =  Students (this name is used as Tab Name)
   > Record = Student Name (which is a field, by default SalesForce will add it)
   >  

## Create Tabs to Newly Created Application
1. click on gear
2. Enter Tabs in Quick Find on Left side of Search
3. Select the Custom Oject
4. Select Tab Style
5. Click On Next
6. Verify Profiles for Dafault On
7. Click On Next
8. Select the App where you want to display the TAB
9. Click on Save Button


## RelationShip
- 6 types
   - self
   - lookup
   - master-detail
   - many 2 many
   - hierarchial
   - rollup summary
- all relationship fields will have search/magnifying glass icon
- Record Name field will be used to show the relationship field in the object
   - record name field is present in the new object creation

### Self Relationship
- Same object will refer back to itelf
- Ex : One student refers another student 



### Lookup vs Master-Details Relationship

| # | Lookup | Master-Details Relationship | 
| :---: | :--- | :--- |
|1|not a mandatory|is mandatory
|2|editable|read-only
|3|child record will not be deleted if the parent is deleted|child record will be deleted if the parent is deleted
|4|40 lookup per object|2 objects are needed
|5|inheritance not possible|inheritance possible 
|6|rollsups not possible|rollsups possible
|7|if record esists, we can create lookup|if record exists, we cannot create relationship
|8|pencil symbol|magnifying class will be displayed

#### Errors in Master-Details Relationship 
| # | Error | Steps | 
| :---: | :--- | :--- |
|1|error create relationship|<ol><li>Create lookup relationship</li><li>Update lookup field data in the object</li><li>change the lookup field type to master-details relationship</li></ol> 


### Many to Many
> 3 objects are needed
> 2 are parents and 3 is child object which is called as common object
> child or common object are called as junction object
> Ex : Student, Batch & Course
   - Student is junction
   - Batch & Course are parent
   - In student, create a field as below
      - Course -> Master Detail Releationship
      - Batch -> Master Detail Releationship
       
### Roll-up Summary
- roll-up field is available for master-detail relationship
- in general, child will refer the parent object
- roll-up summary field can be created in parent object where all the child summary information can be saved
- summarized functions
   - min
   - max
   - sum
   - count
- Ex : Student (child) and batches (parent)
   - Goto batch object -> fields & releationship -> New -> Roll-up Summary -> Next
   - Field Label - Student Counts -> Next
   - Summary Object -> Select from Drop Down
   - Click on the Count radio button -> Next
   - Verify System Administrator -> Next -> Next -> Save
 
### Hierarchial Relationship
- Can be created on the user object


## Field Dependencies
- Use Case
  - Lets say you have created country state, city field (picklist)
  - When user creates a new student and selects the country as India, then state should display only Indian States
- Setup => Object Manager -> Student -> Fields and Relationship -> Field Dependencies
- Controlling Field -> Country
- Dependent Field -> State

## PickList
- 3 types of picklists:
  - Standard
  - Custom
  - Custom Multi-Select
-
## Formula Fields
- Formula fields are readonly
- SalesForce will calculate the data based on the user defined formula/expression
- compilation capacity is 4000 charecters
- Go to Object -> Fields & Relationship -> New -> Formula
  - Field Name  =
  - Field Label =
  - Return Type
  - Next
  - Formula Expression - Simple or Advanced     


## Page Layout
- 

## Record Types
- assign different page layouts, different picklist values to different uses associated to different profiles
- Record Types indirectly controls the Page Layout
- Use Case
  - Display the unique identified in the Student Object based on the country
    - SSN (US), Aadhar Number (Bharat), Nation Insurance Number (UK)
  - 3 Page Layouts are requirement to meet the above requirement
  - Step # 1 : Create 3 fields (SSN, Aadhar Nbr, National Insurance Nbr) in the student object
  -  Step # 2 : Create Page Layout for Bharat
     - Object -> Page Layout -> New -> Remove SSN & National Insurance Nbr Fields
  -  Step # 3 : Create Page Layout for US
     - Object -> Page Layout -> New -> Remove SSN & National Insurance Nbr Fields
  -  Step # 4 : Create Page Layout for Uk
  -  Step # 4 : Create Record Types (follow the below process for other countries)
     - Object -> Record Types -> New
       - Enter Field Name and Field Label -> Bharat;
       - Select System Adminstrator
       - Select Page Layout
       - Click Save
       - Select the pick list by editing (add only Bharat data and remove the other countries data from the select boxes)

## Validation Rules
- checks for the below before saving the record in the salesforce db
  - field length
  - field type
  - unique
- 
