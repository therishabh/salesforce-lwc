# Salesforce LWC

##### Table of Contents  
1. [Lightning Framework](#lightning-framework)
2. [Web Stack Transformation](#web-stack-transformation)
3. [Conditional Rendering](#conditional-rendering)
4. [Create Static Resources](#create-static-resources)
5. [Navi](#navi)
6. [Base Lightning Components](#base-lightning-components)
    1. [Introduction to Work With Data In LWC](#ss)
    2. [Introduction to Work With Data In LWC](#ss)
7. [Base Lightning Components](#base-lightning-components)
8. 
     


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
## Create Static Resources
https://developer.salesforce.com/docs/platform/lwc/guide/create-resources.html

## Base Lightning Components
### Introduction to Work With Data In LWC


