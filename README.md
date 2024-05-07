# Salesforce LWC

##### Table of Contents  
1. [Lightning Framework](#lightning-framework)
2. [Web Stack Transformation](#web-stack-transformation)
3. [Conditional Rendering](#conditional-rendering)
4. [Setter Method](#setter-method)
5. [Create Static Resources](#create-static-resources)
6. [Internationalization](#internationalization)
7. [Base Lightning Components](#base-lightning-components)
    1. [Introduction to Work With Data In LWC](#introduction-to-work-with-data-in-lwc)
    2. [Lightning Data Service](#lightning-data-service)
    3. [Base Lightning Components](#base-lightning-components-1)
    4. [lightning-record-form](#lightning-record-form)
    5. [lightning-record-view-form](#lightning-record-view-form)
    6. [lightning-record-edit-form](#lightning-record-edit-form)
    7. [Custom Validation in lightning-record-edit-form](#custom-validation-in-lightning-record-edit-form)
8. [Base Lightning Components](#base-lightning-components)
9. [Lightning Data Service Wire Adapter and Functions](#lightning-data-service-wire-adapter-and-functions)
    1. [wire Service](#wire-service)
    2. [How @wire is reactive](#how-wire-is-reactive)
    3. [getObjectInfo adapter](#getobjectinfo-adapter)
    4. [getObjectInfos adapter](#getObjectInfos-adapter)
    5. [getPicklistValues adapter](#getPicklistValues-adapter)
    6. [getPicklistValuesByRecordType adapter](#getPicklistValuesByRecordType-adapter)
    7. [getRecord adapter](#getRecord-adapter)
    8. [getFieldValue & getFieldDisplayValue adapter](#getfieldvalue--getfielddisplayvalue)
     


## Lightning Framework
The Lightning Component framework is a Ul framework for developing single page applications for mobile and desktop devices.

Lightning Components using two programming models.
1. Aura Components Model
2. Lightning Web Component Model

### Web Stack Transformation
![Screenshot Capture - 2024-04-27 - 13-05-53](https://github.com/therishabh/salesforce-lwc/assets/7955435/7536dde6-77c4-4ee1-a869-e862935c0876)

### Aura vs LWC
https://www.absyz.com/difference-between-aura-and-lwc/

### What is Lightning Web Components
Lightning Web Components is a new programming model for building Lightning components. It uses the core concepts of Web Standards

#### Benefits
1. Lightweight framework
2. Better Performance
3. No need to learn different framework to develop application in Salesforce
4. Interoperability with lightning Aura components
5. Better testing using Jest
6. Better Security

#### Lightning Experience
Lightning experience is the new user interface (Ul) for salesforce installations. It is a significant upgrade from the Salesforce Classic view, brining modern appearance and functionality to the salesforce Platform.

![Screenshot Capture - 2024-04-27 - 13-14-33](https://github.com/therishabh/salesforce-lwc/assets/7955435/dbda5764-608d-4ceb-8c59-02997dfa6d6c)

### Salesforce Developer Experience(DX)
It is a set of tools that streamlines the entire development life cycle. It improves team development and collaboration, facilitates automated testing and continuous integration, and makes the release cycle more efficient and agile.

1. Visual Studio Code
2. Salesforce CLI
3. Salesforce Extension Pack

## Setting Up My Domain and Dev Hub
Setup my domain in for salesforce org.

Choose a unique name
![Screenshot Capture - 2024-04-27 - 13-24-40](https://github.com/therishabh/salesforce-lwc/assets/7955435/2735bc98-9ab1-402f-bef2-b299f0df9587)

Deploy to users
![Screenshot Capture - 2024-04-27 - 13-26-42](https://github.com/therishabh/salesforce-lwc/assets/7955435/749f08e4-f7e8-4ced-aa5e-ef7931675275)

##### Dev Hub
Once you'll enable Dev Hub then you can not disable it.

![Screenshot Capture - 2024-04-27 - 13-28-28](https://github.com/therishabh/salesforce-lwc/assets/7955435/01b7a0d3-6323-4ea4-837a-6f461b0e156a)

## Setting Up Project and Scratch Org
We'll create project with the help of Visual studio and it's extension Salesforce Extension Pack

Following steps we need to follow for setting up project

Step 1: Open Visual Studio and then click on View and then select Command Palette..
![Screenshot 2024-04-27 at 1 46 36 PM (2)](https://github.com/therishabh/salesforce-lwc/assets/7955435/b26f3823-67ca-4c92-8396-15a01fa7acd9)

Step 2: Type SFDX _(Salesforce Developer Experience)_ in command palette then dropdown will be there then select create project with Manifest.

![Screenshot 2024-04-27 at 1 46 18 PM](https://github.com/therishabh/salesforce-lwc/assets/7955435/337b883b-bf49-4e60-97d1-2c40f7dced01)
![Screenshot 2024-04-27 at 1 50 47 PM](https://github.com/therishabh/salesforce-lwc/assets/7955435/72f02ede-a35f-4537-80cc-12b64f1d43e5)
![Screenshot 2024-04-27 at 1 51 23 PM](https://github.com/therishabh/salesforce-lwc/assets/7955435/7c81b5ab-f97b-474b-990a-75f727af0d00)
![Screenshot 2024-04-27 at 1 51 37 PM](https://github.com/therishabh/salesforce-lwc/assets/7955435/dc58214d-cc25-47cb-9d0d-3a4101ca2e9e)

Step 3: After creating a project, authorize a Dev Hub, that means connect that project with salesforce application.

![Screenshot 2024-04-27 at 2 18 42 PM](https://github.com/therishabh/salesforce-lwc/assets/7955435/a310ed6e-d899-4ff1-b8ba-30dbcbd4684d)
<img width="721" alt="Screenshot 2024-04-27 at 3 06 10 PM" src="https://github.com/therishabh/salesforce-lwc/assets/7955435/4b590854-6051-4907-ab42-0df735b00f9c">

Step 4: Create Scratch org and connect that scratch org with project. **Before create scratch org we need to add hasSampleData key into config json and set that value true.**

![Screenshot 2024-04-27 at 3 24 16 PM](https://github.com/therishabh/salesforce-lwc/assets/7955435/ccc49f67-3251-4b28-a7bc-fe7e10bcf3ac)
![Screenshot 2024-04-27 at 3 24 48 PM](https://github.com/therishabh/salesforce-lwc/assets/7955435/f283edc1-5977-46bb-963e-cb53c5392743)
![Screenshot 2024-04-27 at 3 26 07 PM](https://github.com/therishabh/salesforce-lwc/assets/7955435/f461884a-047a-4596-9cfd-c918934ea19c)
![Screenshot 2024-04-27 at 3 26 22 PM](https://github.com/therishabh/salesforce-lwc/assets/7955435/1840247a-073d-4f05-9c3d-f1cbe91c30bb)
![Screenshot 2024-04-27 at 3 26 33 PM](https://github.com/therishabh/salesforce-lwc/assets/7955435/8bac4a07-9c68-4f39-b0a0-2352ad7566c6)
![Screenshot 2024-04-27 at 3 30 02 PM](https://github.com/therishabh/salesforce-lwc/assets/7955435/c143454f-870d-4f58-b275-26bf1bc4f274)

## Create First Component in LWC

#### Component Naming Convention
The folder and its files must follow these naming rules.
• Must begin with a lowercase letter
• Contain only alphanumeric or underscore characters
• Must be unique in the namespace
• Can't include whitespace
• Can't end with an underscore
• Can't contain two consecutive underscores
• Can't contain a hyphen (dash)

#### Two ways to Create Component
1. Using Terminal

```terminal
sfdx force:lightning:component:create --type lwc -n helloWorld
```

2. Using Command Palette </br>
VsCode => View => Command Palette => Type Create Lightning Web Component => Hit Enter => Enter desired filename => hit enter => Again hit enter to choose default path

![Screenshot 2024-04-27 at 5 45 43 PM](https://github.com/therishabh/salesforce-lwc/assets/7955435/50a613bf-f7a0-48eb-a15c-9f2b2519b109)

#### Component Folder Structure

![Screenshot Capture - 2024-04-27 - 17-47-09](https://github.com/therishabh/salesforce-lwc/assets/7955435/2f821429-dbd5-4b0f-b8a1-0b0fb92ca57b)

#### Naming Conventions for LWC

1. **camelCase:** Each word in the middle of the respective phrase begins with a capital letter.
2. **PascalCase:** It is same like Camel Case where first letter always is capitalized.
3. **kebab-case:** Respective phrase will be transferred to all lowercase with hyphen(-) separating words.

| Case Name  | camelCase | PascalCase | kabab-case |
| ------------- | ------------- | ------------- | ------------- |
| Example  | helloWorld  | HelloWorld  | hello-world  |
| Usage  | component Name  | Component class Name  | Component reference and HTML attribute name  |

## Component Deployment

- First of all we need to configure xml file of newly created component, we need to add targets and isExposed should be true.
```xml
<?xml version="1.0" encoding="UTF-8"?>
<LightningComponentBundle xmlns="http://soap.sforce.com/2006/04/metadata">
    <apiVersion>59.0</apiVersion>
    <isExposed>true</isExposed>
    <targets>
        <target>lightning__AppPage</target>
    </targets>
</LightningComponentBundle>
```

### Local Properties and Data Binding
- variables which are declared in js file are local properties
- Data binding in the Lightning web component is a synchronization between the controller and the template (HTML)
- ![Screenshot Capture - 2024-04-28 - 01-43-30](https://github.com/therishabh/salesforce-lwc/assets/7955435/98c5e2d0-8f93-43b0-a3e8-7ef3c36db960)

#### Things to remember

1) In template we can access property value directly if it's primitive or object.
2) Dot notation is used to access the property from an object
3) LWC doesn't allow computed expressions like Names [2] or {2+2}
4) The property in f } must be a valid JavaScript identifier or member expression. Like {name} or {user.name}
5) Avoid adding spaces around the property, for example, { data }

### Methods and Two way Data binding
Example : See getters section js and HTML file

### @track properties
When a field contains an object or an array, there's a limit to the depth of changes that are tracked. To tell the framework to observe changes to the properties of an object or to the elements of an array, decorate the field with @track.

**Normal Property vs @track property**
Without using @track, the framework observes changes that assign a new value to a field/property. If the new value is not === to the previous value, the component re-renders.

Example : See getters example

### Getters

#### What is Getter and when to use it
![Screenshot Capture - 2024-04-29 - 02-02-17](https://github.com/therishabh/salesforce-lwc/assets/7955435/9412482b-8985-4ccf-88b3-e5df3d759c8c)

File : helloWorld.js
```javascript
import { LightningElement, track } from "lwc";

export default class HelloWorld extends LightningElement {
  fullName = "Rishabh Agrawal";
  course = "Aura";

  @track address = {
    country: "India",
    city: "Delhi",
    pincode: 112233
  };

  users = ["Risahbh", "Shikha", "Madhav", "Ram"];
  num_1 = 10;
  num_2 = 20;

  onKeyUpHandler(event) {
    this.course = event.target.value;
  }

  onCityKeyUpHandler(event) {
    this.address.city = event.target.value;
  }

  get getFirstUser() {
    return this.users[0];
  }

  get calculationValue() {
    return this.num_1 * this.num_2;
  }
}

```

File : helloWorld.html
```html
<template>
  <lightning-card title="Two way data binding">
    <div class="slds-m-around_medium">
      <lightning-input
        type="text"
        label="Enter Course Name"
        onkeyup={onKeyUpHandler}
      ></lightning-input>
      <div>Hello, {fullName}, learning new course that is : {course}</div>
    </div>
  </lightning-card>

  <lightning-card title="@track Property">
    <div class="slds-m-around_medium">
      <lightning-input
        type="text"
        label="Enter City Name"
        onkeyup={onCityKeyUpHandler}
      ></lightning-input>
      <div>I am from {address.city} city.</div>
    </div>
  </lightning-card>

  <lightning-card title="Getter function">
    <div class="slds-m-around_medium">
      <div>{getFirstUser}</div>
      <div>The multiplication of {num_1} and {num_2} is {calculationValue}</div>
    </div>
  </lightning-card>
</template>

```

## Conditional Rendering

File : conditionalComponent.html
```html
<template>
    <lightning-card title="Conditional rendring">

        <div class="slds-m-around_medium">
            <lightning-button variant="brand" label="Show Data" title="Show Data" onclick={handleShowDataButtonClick} class="slds-m-left_x-small"></lightning-button>
            <div>
                <template lwc:if={isVisible}>
                    Button Clicked
                </template>
                <template lwc:else>
                    Please click button to show data.
                </template> 
            </div>
            <div class="slds-m-top_medium">
                <lightning-input type="text" label="Enter some text" onkeyup={handleCondtionalInputText}></lightning-input>
                <template lwc:if={checkHelloText}>
                    yooo... you typed hello
                </template>
                <template lwc:elseif={checkJapanText}>
                    yooo... you typed Japan
                </template>
            </div>
        </div>
    </lightning-card>
</template>
```

File : conditionalComponent.js
```javascript
import { LightningElement } from "lwc";

export default class ConditionalComponent extends LightningElement {
  isVisible = false;
  text;

  handleShowDataButtonClick() {
    this.isVisible = true;
  }

  handleCondtionalInputText(event) {
    this.text = event.target.value;
  }

  get checkHelloText() {
    return this.text?.toLowerCase() === 'hello'
  }

  get checkJapanText() {
    return this.text?.toLowerCase() === 'japan'
  }
}

```

## Setter Method
This method is use to modified the data coming from parent component. If Object is passed as data to setter, to mutate the object we have to create a shallow copy.
File Name : setterDemoChild.js
```javascript
import { LightningElement, api } from 'lwc';

export default class SetterDemoChild extends LightningElement {
    userDetail

    @api
    get detail(){
        return  this.userDetail
    }
    set detail(data){
        let newAge = data.age*2
        this.userDetail = {...data, age:newAge, "location":"Melbourne"}
    }
}
```

File Name : setterDemoChild.html
```html
<template>
    <p><strong>Name</strong> - {detail.name}</p>
    <p><strong>Age</strong> - {detail.age}</p>
    <p><strong>location</strong> - {detail.location}</p>
</template>
```


File Name : setterDemoParent.js
```javascript
import { LightningElement } from 'lwc';

export default class SetterDemoParent extends LightningElement {
    userDetails = {
        name:"salesforcetroop",
        age:25
    }
}
```

File Name : setterDemoParent.html
```html
<template>
    <lightning-card title="Setter Method Demo">
        <c-setter-demo-child detail={userDetails}></c-setter-demo-child>
    </lightning-card>
</template>
```




## Create Static Resources
https://developer.salesforce.com/docs/platform/lwc/guide/create-resources.html

## Internationalization
Import internationalization properties from the @salesforce/i18n scoped module. Lightning web components have internationalization properties that you can use to adapt your components for users worldwide, across languages, currencies, and timezones.

File Name : internationalization.js
```javascript
import { LightningElement } from 'lwc';
import LOCALE from '@salesforce/i18n/locale';
import CURRENCY from '@salesforce/i18n/currency';
import DIR from '@salesforce/i18n/dir';
import LANG from "@salesforce/i18n/lang";

export default class Internationalization extends LightningElement {
    dir = DIR;
    lang = LANG;

    today = new Date();
    formatedDate = new Intl.DateTimeFormat(LOCALE).format(this.today);

    number  = 45847584.33;
    formatedNumber = new Intl.NumberFormat(LOCALE, {
        style : 'currency',
        currency : CURRENCY,
        currencyDisplay : 'symbol'
    }).format(this.number)
}
```

File Name : internationalization.html
```html
<template>
    <lightning-card title="Internationalization">
        <div class="slds-p-around_medium">
            <p dir={dir} lang={lang}>
                {formatedNumber} {formatedDate}
            </p>
        </div>
    </lightning-card>
</template>
```

## Base Lightning Components
### Introduction to Work With Data In LWC
There are many ways of interacting with Salesforce data in the Lightning web components. Knowing which approach to use for a particular use case helps you to write less code, easier code, and code that is more maintainable. The efficiency of your components is improved by using the best solution for each situation.

![Screenshot Capture - 2024-05-05 - 18-58-24](https://github.com/therishabh/salesforce-lwc/assets/7955435/b7dbe4e8-4133-4b16-9679-867bbee91b14)

### Lightning Data Service
Lightning Data Service is a centralized data caching framework and it is built on top of User Interface API 
https://developer.salesforce.com/docs/platform/lwc/guide/data-ui-api.html

![Screenshot Capture - 2024-05-05 - 19-01-36](https://github.com/therishabh/salesforce-lwc/assets/7955435/25ef2090-c02f-4a08-9390-3b0eb9f6de3c)

### Base Lightning Components
Base Lightning Components are built on Lightning Data Service. So, Lightning Data Service is used behind the scenes by base components and inherits its caching and synchronisation capabilities

There are three types of base lightning components built on LDS are

1) lightning-record-form
2) lightning-record-edit-form
3) lightning-record-view-form

**When to Use these form?**
- Create a metadata-driven Ul or form-based Ul similar to the record detail page in Salesforce.
- Display record values based on the field metadata.
- Hide or show localized field labels.
- Display the help text on a custom field.
- Perform client-side validation and enforce validation rules.

https://developer.salesforce.com/docs/platform/lwc/guide/data-get-user-input.html

- lightning-record-edit-form—Displays an editable form.
- lightning-record-view-form—Displays a read-only form.
- lightning-record-form—Supports edit, view, and read-only modes.

<img width="1057" alt="Screenshot 2024-05-05 at 7 08 58 PM" src="https://github.com/therishabh/salesforce-lwc/assets/7955435/14ba5360-dcd4-4102-9787-aa2f5c90b933">

For most use cases, lightning-record-form provides a great starting point. It combines and simplifies the functionality of lightning-record-view-form and lightning-record-edit-form. All three components support a multi column layout. For example, you can use <div class="slds-grid"> to create a column.

### lightning-record-form
Use the lightning-record-form component to quickly create forms to add, view, or update a record.

The lightning-record-form component provides these helpful features:
- Switches between view and edit modes automatically when the user begins editing a field in a view form
- Provides Cancel and Save buttons automatically in edit forms
- Uses the object's default record layout with support for multiple columns
- Loads all fields in the object's compact or full layout, or only the fields you specify

lightning-record-form is less customizable. To customize the form layout or provide custom rendering of record data, use lightning-record-edit-form (add or update a record) and lightning-record-view-form (view a record).

**Key Attributes**
- **object-api-name** - This attribute is always required. The lightning-record-form component requires you to specify the object-api-name attribute to establish the relationship between a record and an object.
_Note- Event and Task objects are not supported._
- **record-id** - This attribute is required only when you're editing or viewing a record.
- **fields** - pass record fields as an array of strings. The fields display in the order you list them.
- **layout-type** - Use this attribute to specify a Full or Compact layout. Layouts are typically defined (created and modified) by administrators..
- **modes** - This form support three mode
    - **edit** - Creates an editable form to add a record or update an existing one.. Edit mode is the default when record-id is not provided, and displays a form to create new records.
    - **view** - Creates a form to display a record that the user can also edit. The record fields each have an edit button. View mode is the default when record-id is provided.
    - **readonly** - Creates a form to display a record that the user can also edit
- **columns** - Use this attribute to show multiple columns in the form

File Name : recordFormDemo.js
```javascript
import { LightningElement, api } from 'lwc';
import { ShowToastEvent } from 'lightning/platformShowToastEvent';

import ACCOUNT_OBJECT from '@salesforce/schema/Account'
import NAME_FIELD from '@salesforce/schema/Account.Name'
import ANNUAL_REVENUE_FIELD from '@salesforce/schema/Account.AnnualRevenue'
import TYPE_FIELD from '@salesforce/schema/Account.Type'
import INDUSTRY_FIELD from '@salesforce/schema/Account.Industry'
export default class RecordFormDemo extends LightningElement {
    @api recordId
    @api objectApiName
    objectName = ACCOUNT_OBJECT
    fieldList = [NAME_FIELD, ANNUAL_REVENUE_FIELD, TYPE_FIELD, INDUSTRY_FIELD]

    successHandler(event){ 
        console.log(event.detail.id)
        const toastEvent = new ShowToastEvent({ 
            title:"Account created",
            message:"Record ID: "+ event.detail.id,
            variant:"success"
        })
        this.dispatchEvent(toastEvent)
    }
}
```

File Name : recordFormDemo.html
```html
<template>
    <lightning-card title="Create record using lightning-record-form">
        <lightning-record-form
        object-api-name={objectName}
        fields={fieldList}
        onsuccess={successHandler}
        ></lightning-record-form>
    </lightning-card>

    <lightning-card title="Display record using lightning-record-form">
        <lightning-record-form
        record-id="001N000001zcknoIAA"
        object-api-name={objectName}
        fields={fieldList}
        ></lightning-record-form>
    </lightning-card>

    <lightning-card title="Display record in readonly mode using lightning-record-form">
        <lightning-record-form
        record-id="001N000001zcknoIAA"
        object-api-name={objectName}
        fields={fieldList}
        mode="readonly"
        ></lightning-record-form>
    </lightning-card>

    <lightning-card title="Edit record using lightning-record-form">
        <lightning-record-form
        record-id="001N000001zcknoIAA"
        object-api-name={objectName}
        fields={fieldList}
        mode="edit"
        columns="2"
        ></lightning-record-form>
    </lightning-card>

    <!-- that will only work in record page because we are using recordId and objectApiName which will automatic fill when we will use this component in record page-->
    <lightning-card title="Edit record with layout using lightning-record-form">
        <lightning-record-form
        record-id={recordId}
        object-api-name={objectApiName}
        mode="edit"
        columns="2"
        layout-type="Compact"
        ></lightning-record-form>
    </lightning-card>

</template>
```

### lightning-record-view-form
- Use the lightning-record-view-form component to create a form that displays Salesforce record data for specified fields associated with that record. The fields are rendered with their labels and current values as read-only.
- You can customize the form layout or provide custom rendering of record data. If you don't require customizations, use lightning-record-form instead.
- To specify read-only fields, use lightning-output-field components inside lightning-record-view-form.

File Name : recordViewFormDemo.js
```javascript
import { LightningElement } from 'lwc';

export default class RecordViewFormDemo extends LightningElement {}
```

File Name : recordViewFormDemo.html
```html
<template>
    <lightning-card title="lightning record view form">
        <lightning-record-view-form
        object-api-name="Account"
        record-id="001N000001zcknoIAA"
        >
        <div class="slds-grid slds-gutters">
            <div class="slds-col slds-size_6-of-12">
                <lightning-output-field field-name="Name"></lightning-output-field>
                <lightning-output-field field-name="Phone"></lightning-output-field>
                <lightning-output-field field-name="Industry"></lightning-output-field>
            </div>
            <div class="slds-col slds-size_6-of-12">
                <lightning-output-field field-name="AnnualRevenue"></lightning-output-field>
            </div>
        </div>
        </lightning-record-view-form>
    </lightning-card>
</template>
```

### lightning-record-edit-form
- This component is used to create and edit the records.
- It provides custom layout of fields and custom rendering of record data.

File Name : recordEditForm.js
```javascript
import { LightningElement } from 'lwc';
import CONTACT_OBJECT from '@salesforce/schema/Contact'
import NAME_FIELD from '@salesforce/schema/Contact.Name'
import TITLE_FIELD from '@salesforce/schema/Contact.Title'
import PHONE_FIELD from '@salesforce/schema/Contact.Phone'
import EMAIL_FIELD from '@salesforce/schema/Contact.Email';
import ACCOUNT_FIELD from '@salesforce/schema/Contact.AccountId';
export default class RecordEditForm extends LightningElement {
    objectName = CONTACT_OBJECT
    fields={ 
        accountField:ACCOUNT_FIELD,
        nameField:NAME_FIELD,
        titleField:TITLE_FIELD,
        phoneField:PHONE_FIELD,
        emailField:EMAIL_FIELD
    }

    handleReset(){ 
        const inputFields = this.template.querySelectorAll('lightning-input-field')
        if(inputFields){ 
            Array.from(inputFields).forEach(field=>{ 
                field.reset()
            })
        }
    }
}
```


File Name : recordEditForm.html
```html
<template>
    <lightning-card title="lightning record edit form">
        <lightning-record-edit-form 
        object-api-name={objectName}
        >
            <lightning-messages></lightning-messages>
            <lightning-input-field field-name={fields.accountField}></lightning-input-field>
            <lightning-input-field field-name={fields.nameField}></lightning-input-field>
            <lightning-input-field field-name={fields.titleField}></lightning-input-field>
            <lightning-input-field field-name={fields.phoneField}></lightning-input-field>
            <label class="slds-p-left_x-small">Enter your email</label>
            <lightning-input-field variant="label-hidden" field-name={fields.emailField}></lightning-input-field>
            <lightning-button class="slds-m-around_xx-small" label="cancel" onclick={handleReset}></lightning-button>
            <lightning-button variant="brand" type="submit" class="slds-m-around_xx-small" label="Save"></lightning-button>
        </lightning-record-edit-form>
    </lightning-card>
</template>
```

#### Custom Validation in lightning-record-edit-form

File Name : recordEditForm.js
```javascript
import { LightningElement } from 'lwc';
import ACCOUNT_OBJECT from '@salesforce/schema/Account'
import { ShowToastEvent } from 'lightning/platformShowToastEvent';

export default class RecordEditCustom extends LightningElement {
    objectName = ACCOUNT_OBJECT
    inputValue=''
    handleChange(event){ 
        this.inputValue = event.target.value
    }
    handleSubmit(event){ 
        event.preventDefault()
        const inputCmp = this.template.querySelector('lightning-input')
        const value= inputCmp.value
        if(!value.includes('Australia')){ 
            inputCmp.setCustomValidity("The account name must include 'Australia'")
        } else { 
            inputCmp.setCustomValidity("")
            const fields = event.detail.fields
            fields.Name = value
            this.template.querySelector('lightning-record-edit-form').submit(fields)
        }
        inputCmp.reportValidity()

    }
    successHandler(event){ 
        const toastEvent = new ShowToastEvent({ 
            title:"Account created",
            message: "Record ID: "+ event.detail.id,
            variant:"success"
        })
        this.dispatchEvent(toastEvent)

    }
    handleError(event){ 
        const toastEvent = new ShowToastEvent({ 
            title:"Error creating Account",
            message: event.detail.message,
            variant:"error"
        })
        this.dispatchEvent(toastEvent)
    }
}
```

File Name : recordEditForm.html
```html
<template>
    <lightning-card title="Custom validation in lightning record edit form">
        <lightning-record-edit-form
        object-api-name={objectName}
        onsubmit={handleSubmit}
        onsuccess={successHandler}
        onerror={handleError}
        >
            <lightning-input label="Name"
            value={inputValue}
            onkeyup={handleChange}
            class="slds-m-bottom_x-small"></lightning-input>
    
            <lightning-button class="slds-m-top_small" type="submit" label="Create Account"></lightning-button>
        </lightning-record-edit-form>
    </lightning-card>
</template>
```

## Lightning Data Service Wire Adapter and Functions
### @wire service
**What is @wire service ?**
1. Wire service is built on Lightning Data Service
2. LWC component use @wire in their JavaScript class to read data from one of the wire adapters in the lightning/ui*Api namespace.
3. @wire is a reactive service
4. The wire adapter defines the data shape that the wire service provisions in an immutable stream

File Name : wireDemoUserDetail.js
```javascript
import { LightningElement, wire } from 'lwc';
import { getRecord } from 'lightning/uiRecordApi';
import NAME_FIELD from '@salesforce/schema/User.Name';
import EMAIL_FIELD from '@salesforce/schema/User.Email';
import CITY_FIELD from '@salesforce/schema/User.City';
import id from '@salesforce/user/Id';

const fields = [NAME_FIELD, EMAIL_FIELD, CITY_FIELD]

export default class WireDemoUserDetail extends LightningElement {
    userId = id; // will return current login user id;
    userInfo;
    //005F3000007xXBPIA2

    @wire(getRecord, {recordId: '005F3000007xXBPIA2', fields: ['User.Name', 'User.Email']})
    userDetailHandler({data, error}){
        if(data){
            this.userInfo = data.fields;
            console.log(this.userInfo)
        }else {
            console.error(error)
        }
    }

   
    @wire(getRecord, {recordId: '005F3000007xXBPIA2', fields})
    userData;
    connectedCallback(){
        console.log('userData', this.userData);
    }
    
}
```

File Name : wireDemoUserDetail.html
```html
<template>
    <lightning-card title="User Detail using @wire as function">
        <div class="slds-p-around_medium">
            <template if:true={userInfo}>
                <div>
                    <p>
                        <strong>Name : </strong> {userInfo.Name.value}
                    </p>
                    <p>
                        <strong>Email : </strong> {userInfo.Email.value}
                    </p>
                </div>
            </template>
        </div>
    </lightning-card>

    <div class="slds-m-top_medium"></div>

    <lightning-card title="User Detail using @wire as property" >
        <div class="slds-p-around_medium">
            <template if:true={userInfo}>
                <div>
                    <p>
                        <strong>Name : </strong> {userData.data.fields.Name.value}
                    </p>
                    <p>
                        <strong>Email : </strong> {userData.data.fields.Email.value}
                    </p>
                    <p>
                        <strong>City : </strong> {userData.data.fields.City.value}
                    </p>
                </div>
            </template>
        </div>
    </lightning-card>
</template>
```

Output : </br>
<img width="721" alt="Screenshot 2024-05-06 at 5 57 27 PM" src="https://github.com/therishabh/salesforce-lwc/assets/7955435/4f01e0c9-bd20-429d-ba5c-7197b50c201a">

**How to Import Reference of Salesforce Standard Object**
```javascript
// Syntax
import objectName from '@salesforce/schema/object;

// Example
import ACCOUNT_OBJECT from '@salesforce/schema/Account';
```

**How to Import Reference to Salesforce custom Object**
```javascript
// Syntax
import objectName from '@salesforce/schema/object';

// Example
import PROPERTY_OBJECT from '@salesforce/schema/Property_c';
```

**How to Import References to Salesforce Fields**
```javascript
// Syntax
import FIELD_NAME from '@salesforce/schema/object.field'\

// Example
import ACCOUNT_NAME from '@salesforce/schema/Account.Name'; '
import PROPERTY_NAME from '@salesforce/schema/Property_c.Name';
```

**How to Import Reference to a field via a relationship**
```javascript
// Syntax
import REF_FIELD_NAME from @salesforce/schema/object.relationship.field

// Example
import ACCOUNT_OWNER from '@salesforce/schema/Account.Owner.Name';
```

### How @wire is reactive
By adding “$” to the recordId parameter, we made it reactive. From now, every change of the variable recordId value will run the getRecord function.

```javascript
userId = id; // will return current login user id;
userInfo;

@wire(getRecord, {recordId: '$userId', fields: ['User.Name', 'User.Email']})
userDetailHandler({data, error}){
    if(data){
        this.userInfo = data.fields;
        console.log(this.userInfo)
    }else {
        console.error(error)
    }
}
```

### getObjectInfo adapter
Use this wire adapter to get metadata about a specific object. The response includes metadata describing the object's fields, child relationships, record type, and theme.

```javascript
import { LightningElement, wire } from 'lwc';
import {getObjectInfo} from 'lightning/uiObjectInfoApi'
import ACCOUNT_OBJECT from '@salesforce/schema/Account'
export default class GetObjectInfoDemo extends LightningElement {

    @wire(getObjectInfo, {objectApiName:ACCOUNT_OBJECT})
    objectInfo
}
```

```html
<template>
    <lightning-card title="getObjectInfo Adapter">
        <div class="slds-var-p-around_medium">
            <template if:true={objectInfo.data}>
                <div>defaultRecordTypeId: {objectInfo.data.defaultRecordTypeId}</div>
                <div>Object API Name: {objectInfo.data.apiName}</div>
            </template>
        </div>
    </lightning-card>
</template>
```

### getObjectInfos adapter
Use this wire adapter to get metadata for multiple objects. The response includes metadata describing the fields, child relationships, record type, and theme for each object.

```javascript
import { LightningElement, wire } from 'lwc';
import {getObjectInfos} from 'lightning/uiObjectInfoApi'
import ACCOUNT_OBJECT from '@salesforce/schema/Account'
import OPPORTUNITY_OBJECT from '@salesforce/schema/Opportunity'
export default class GetObjectInfoDemo extends LightningElement {

    objectApiNames = [ACCOUNT_OBJECT, OPPORTUNITY_OBJECT]

    objectInfos
    @wire(getObjectInfos, { objectApiNames: '$objectApiNames' })
    objectInfosHandler({data}){
        if(data){
            console.log(data)
            this.objectInfos = data
        }
    }
}
```

```html
<template>
    <lightning-card title="getObjectInfos Adapter">
        <div class="slds-var-p-around_medium">
            <template if:true={objectInfos}>
                <template for:each={objectInfos.results} for:item="obj">
                    <div key={obj.result.apiName}>
                        <div>Object Api Name - {obj.result.apiName}</div>
                        <div>defaultRecordTypeId - {obj.result.defaultRecordTypeId}</div>
                    </div>
                </template>
            </template>
            
        </div>
    </lightning-card>    
</template>
```

### getPicklistValues adapter
Use this wire adapter to get the picklist values for a specified field.

Syntax
```javascript
import { LightningElement, wire } from 'Iwc';
import { getPicklistvalues } from 'lightning/uiobjectInfoApi';
import INDUSTRY_FIELD from '@salesforce/schema/Account.Industry';

export default class Example extends LightningElement {
    @wire(getPicklistvalues, { recordTypeId: 012000000000000AAA', fieldApiName: INDUSTRY_FIELD })
    propertyOrFunction;
｝
```

> **_NOTE:_**

**recordTypeld -** The ID of the record type. Use the Object Info _defaultRecordTypeId_ property, which is returned from _getObjectInfo_
**fieldApiName -** The API name of the picklist field

**Example**

File Name : getPicklistValuesDemo.js
```javascript
import { LightningElement, wire } from "lwc";
import { getObjectInfo, getPicklistValues } from "lightning/uiObjectInfoApi";
import INDUSTRY_FIELD from "@salesforce/schema/Account.Industry";
import ACCOUNT_OBJECT from "@salesforce/schema/Account";

export default class GetPicklistValuesDemo extends LightningElement {
  industryOptions = [];
  selectedIndustry;

  @wire(getObjectInfo, { objectApiName: ACCOUNT_OBJECT })
  objectInfo;

  @wire(getPicklistValues, {
    recordTypeId: "$objectInfo.data.defaultRecordTypeId",
    fieldApiName: INDUSTRY_FIELD
  })
  industryPicklist({ data, error }) {
    if (data) {
      this.industryOptions = this.generateIndustryOptions([...data.values]);
    } else {
      console.error(error);
    }
  }

  generateIndustryOptions(data){
	return data.map(val => {
		return {
			value : val.value,
			label : val.label
		}
	})
  }

  handleIndustryChange(event) {
    this.selectedIndustry = event.detail.value;
    console.log(this.selectedIndustry);
  }
}

```

File Name : getPicklistValuesDemo.html
```html
<template>
    <lightning-card title="getPicklistValues Demo">
        <div class="slds-var-p-around_medium">
            <lightning-combobox
            name="Industry"
            label="Industry"
            value={value}
            placeholder="Select Industry"
            options={industryOptions}
            onchange={handleIndustryChange} ></lightning-combobox>

    <p>Selected value is: {selectedIndustry}</p>
        </div> 
    </lightning-card>
</template>
```

### getPicklistValuesByRecordType adapter
Use this wire adapter to get the values for every picklist of a specified record type.

Syntax
```javascript
import { LightningElement, wire } from 'Iwc';
import { getPicklistValuesByRecordType } from 'lightning/uiobjectInfoApi';
import ACCOUNT_OBJECT from '@salesforce/schema/Account';

export default class Example extends LightningElement {
    @wire(getPicklistValuesByRecordType, { recordTypeId: 012000000000000AAA', objectApiName: ACCOUNT_OBJECT })
    propertyOrFunction;
｝
```

> **_NOTE:_**

**recordTypeld -** The ID of the record type. Use the Object Info _defaultRecordTypeId_ property, which is returned from _getObjectInfo_
**objectApiName -** The API name of the object

**Example**
File Name : getPicklistValuesByRecordTypeDemo.js
```javascript
import { LightningElement, wire } from 'lwc';
import {getPicklistValuesByRecordType, getObjectInfo} from 'lightning/uiObjectInfoApi'
import ACCOUNT_OBJECT from '@salesforce/schema/Account'
export default class GetPicklistValuesByRecordTypeDemo extends LightningElement {
    ratingOptions
    industryOptions
    selectedRating
    selectedIndustry
    @wire(getObjectInfo, {objectApiName:ACCOUNT_OBJECT})
    objectInfo

    @wire(getPicklistValuesByRecordType, {objectApiName:ACCOUNT_OBJECT, 
        recordTypeId:'$objectInfo.data.defaultRecordTypeId'})
        picklistHandler({data, error}){
            if(data){
                console.log(data)
                this.ratingOptions = this.picklistGenerator(data.picklistFieldValues.Rating)
                this.industryOptions = this.picklistGenerator(data.picklistFieldValues.Industry)
            }
            if(error){
                console.error(error)
            }
        }

    picklistGenerator(data){
        return data.values.map(item=>({"label":item.label, "value":item.value}))
    }

    handleChange(event){
        const {name, value} = event.target
        console.log(name +'==>' +value)
        if(name === 'industry'){
            this.selectedIndustry = value
        }
        if(name === 'rating'){
            this.selectedRating = value
        }
    }
}
```

File Name : getPicklistValuesByRecordTypeDemo.html
```html
<template>
    <lightning-card title="getPicklistValuesByRecordType Adapter">
        <div class="slds-var-p-around_medium">
            <template if:true={ratingOptions}>
                <lightning-combobox
                name="rating"
                label="Rating"
                value={selectedRating}
                placeholder="Select Rating"
                options={ratingOptions}
                onchange={handleChange}></lightning-combobox>
                <p>selectedRating: {selectedRating}</p>
            </template>
            
            <template if:true={industryOptions}>
                <lightning-combobox
                name="industry"
                label="Industry"
                value={selectedIndustry}
                placeholder="Select Industry"
                options={industryOptions}
                onchange={handleChange}></lightning-combobox>
                <p>selectedIndustry: {selectedIndustry}</p>
            </template>
        </div>
    </lightning-card>
</template>
```

### getRecord adapter
Use this wire adapter to get the record's data

Syntax
```javascript
import { LightningElement, wire } from "Iwc';
import { getRecord } from 'lightning/uiRecordApi';
@wire(getRecord, { recordId: string, fields: string|string|], optionalFields?: string|string[])
propertyOrFunction

@wire(getRecord, {
recordId: string,
layoutTypes: string|string[],
modes?: string|string|],
optionalFields?: string|string[])
propertyOrFunction
```
**recordld -** The ID of the record type. </br>
**fields -** A field or an array of fields to return or</br>
**layoutType -** it support two values Compact or Full(default) </br>
**Modes -** used with layout. Values supported are Create, Edit and View (default) </br>
**optionalFields -** a field name or an array of field names. If a field is accessible to the user, it includes in response otherwise it will not throw an error. </br>


**Example** </br>
File Name : getRecordDemo.js
```javascript
import { LightningElement, wire, api } from 'lwc';
import {getRecord} from 'lightning/uiRecordApi'
import NAME_FIELD from '@salesforce/schema/Account.Name'
import OWNER_NAME_FIELD from '@salesforce/schema/Account.Owner.Name'
import ANNUAL_REVENUE_FIELD from '@salesforce/schema/Account.AnnualRevenue'
export default class GetRecordDemo extends LightningElement {
    name
    owner
    AnnualRevenue
    @api recordId
    // @wire(getRecord, {recordId:'$recordId',
    //  fields:[NAME_FIELD, OWNER_NAME_FIELD, ANNUAL_REVENUE_FIELD]})
    @wire(getRecord, {recordId:'$recordId',
     layoutTypes:['Full'], modes:['View']})
     accountHandler({data}){
         if(data){
             console.log(data)
             this.name = data.fields.Name.displayValue ? data.fields.Name.displayValue:
             data.fields.Name.value
             this.AnnualRevenue = data.fields.AnnualRevenue.displayValue ? data.fields.AnnualRevenue.displayValue:
             data.fields.AnnualRevenue.value
             this.owner = data.fields.Owner.displayValue ? data.fields.Owner.displayValue:
             data.fields.Owner.value

         }
     }
}
```

File Name : getRecordDemo.html
```html
<template>
    <lightning-card title="getRecord Adapter">
        <div class="slds-p-around_medium">
            <div>Name - {name}</div>
            <div>owner - {owner}</div>
            <div>AnnualRevenue - {AnnualRevenue}</div>
        </div>
    </lightning-card>
</template>
```

### getFieldValue & getFieldDisplayValue
**getFieldValue**
Use this to gets a field's value from a record

Syntax
```js
import { getFieldValue } from 'lightning/uiRecordApi';
getFieldValue(record: Record, field: string)
```

**getFieldDisplayValue**
Use this to gets a field's value in formatted and localized format from a record

Syntax
```js
import { getFieldDisplayValue } from 'lightning/uiRecordApi';
getFieldDisplayValue(record, field)
```


















