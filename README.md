# Salesforce LWC

##### Table of Contents  
1. [Lightning Framework](#lightning-framework)
2. [Web Stack Transformation](#web-stack-transformation)
3. [Setting Up My Domain and Dev Hub](#setting-up-my-domain-and-dev-hub)
4. [Setting Up Project and Scratch Org](#setting-up-project-and-scratch-org)
5. [Create First Component in LWC](#create-first-component-in-lwc)
6. [Component Deployment](#component-deployment)
7. [Local Properties and Data Binding](#local-properties-and-data-binding)
8. [@track properties](#track-properties)
9. [Getters](#getters)
10. [Conditional Rendering](#conditional-rendering)
11. [Template Looping (for:each and iterator)](#template-looping-foreach-and-iterator)
    1. [for:each loop](#foreach-loop)
    2. [iterator loop](#iterator-loop)
12. [Component Composition](#component-composition)
13. [Accessing Elements in LWC](#accessing-elements-in-lwc)
14. [Parent to child Communication](#parent-to-child-communication)
15. [Parent to Child Communication by calling the Child method from the parent component](#parent-to-child-communication-by-calling-the-child-method-from-the-parent-component)
16. [Child to Parent Communication](#child-to-parent-communication)
17. [Setter Method](#setter-method)
18. [Slot](#slot)
19. [Create Static Resources](#create-static-resources)
20. [Internationalization](#internationalization)
21. [Navigation Service](#navigation-service)
22. [Base Lightning Components](#base-lightning-components)
    1. [Introduction to Work With Data In LWC](#introduction-to-work-with-data-in-lwc)
    2. [Lightning Data Service](#lightning-data-service)
    3. [Base Lightning Components](#base-lightning-components-1)
    4. [lightning-record-form](#lightning-record-form)
    5. [lightning-record-view-form](#lightning-record-view-form)
    6. [lightning-record-edit-form](#lightning-record-edit-form)
    7. [Custom Validation in lightning-record-edit-form](#custom-validation-in-lightning-record-edit-form)
23. [Base Lightning Components](#base-lightning-components)
24. [Lightning Data Service Wire Adapter and Functions](#lightning-data-service-wire-adapter-and-functions)
    1. [wire Service](#wire-service)
    2. [How @wire is reactive](#how-wire-is-reactive)
    3. [getObjectInfo adapter](#getobjectinfo-adapter)
    4. [getObjectInfos adapter](#getObjectInfos-adapter)
    5. [getPicklistValues adapter](#getPicklistValues-adapter)
    6. [getPicklistValuesByRecordType adapter](#getPicklistValuesByRecordType-adapter)
    7. [getRecord adapter](#getRecord-adapter)
    8. [getFieldValue & getFieldDisplayValue adapter](#getfieldvalue--getfielddisplayvalue)
    9. [getListInfoByName adapter](#getListInfoByName-adapter)
    10. [createRecord](#createRecord)
25. [Apex In LWC](#apex-in-lwc)
    1. [Expose Apex Methods to LWC](#expose-apex-methods-to-lwc)
    2. [Import Apex Methods](#import-apex-methods)
    3. [Wire Apex Method](#wire-apex-method)
    4. [Wire Apex Method with Parameters](#wire-apex-method-with-parameters)
    5. [Call Apex Methods Imperatively](#call-apex-methods-imperatively-with-and-without-parameters)

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

## Template Looping (for:each and iterator)
There are many scenarios in which we have to render the same set of elements with mostly same styling with different data in the HTML. To solve this issue, we have template looping in the LWC
**Template Looping Types**
1. for:Each
2. iterator

### for:each loop
Below is the syntax of the for:each loop
```js
<template for:each={array} for:item="currentItem" for:index="index">
  -----Here your repeatable template comes-----
</template>
```
![Screenshot 2024-05-09 at 11 47 26 PM](https://github.com/therishabh/salesforce-lwc/assets/7955435/f115df74-b4ac-4e07-b926-2f597d7926e5)

**What is key and it's importance in the loop**
- A **key** is a special string attribute you need to include to the first element inside the template when creating lists of elements.
- Keys help the LWC engine identify which items have changed, are added, or are removed.
- The best way to pick a key is to use a string that uniquely identifies a list item among its siblings.

> **Note :** The key must be a string or a number, it can't be an object. You can't use the index as a value for the key.

**Example**
File Name : templateLoopingForEach.js
```js
import { LightningElement } from "lwc";
export default class TemplateLoopingForEach extends LightningElement {
  carList = ["Ford", "Audi", "Maruti", "Hyundai", "Mercedes"];
  programmingList = [
    {
      id: "06868",
      language: "HTML"
    },
    {
      id: "19797",
      language: "CSS"
    },
    {
      id: "298789",
      language: "Javascript"
    },
    {
      id: "398798",
      language: "Apex"
    },
    {
      id: "48967",
      language: "Aura"
    },
    {
      id: "58798",
      language: "Java"
    }
  ];
}
```

File Name : templateLoopingForEach.html
```html
<template>
  <!-- Card for for:each demo with an array -->
  <lightning-card title="for:each demo with array" icon-name="custom:custom14">
    <ul class="slds-m-around_medium">
      <template for:each={carList} for:item="car">
        <a href="#" class="list-group-item list-group-item-action" key={car}>{car}</a>
      </template>
    </ul>
  </lightning-card>

  <hr />

  <!-- Card for for:each demo with an array of objects -->
  <lightning-card
    title="for:each demo with array of objects"
    icon-name="custom:custom14"
  >
    <ul class="slds-m-around_medium">
      <template for:each={programmingList} for:item="program">
        <a
          href="#"
          class="list-group-item list-group-item-action"
          key={program.id}
          >{program.language}
	</a>
      </template>
    </ul>
  </lightning-card>
</template>
```

### iterator loop
To apply a special behavior to the first or last item in a list we prefer iterator over for:each

Below is the syntax of the iterator loop
```js
<template iterator:iteratorName={array}>
  -----Here your repeatable template comes-----
</template>
```
![Screenshot 2024-05-09 at 11 55 25 PM](https://github.com/therishabh/salesforce-lwc/assets/7955435/48ec0601-2f97-4faa-b186-767387d1d1b7)

**Properties of iterator name**
Using iterator name you can access the following properties
1. value — The value of the item in the list. Use this property to access the properties of the array. For example -iteratorName.value.propertyName
2. index — The index of the item in the list. For example -iteratorName.index
3. first — A boolean value indicating whether this item is the first item in the list. For example -iteratorName.first
4. last — A boolean value indicating whether this item is the last item in the list. For example -iteratorName.last

> Note : In iterator loop array item will be store one by one in iteratorName (as per syntax) and those item not directly accessible from iteratorName we will get array item inside value object example -iteratorName.value.propertyName

**Example**

File Name : templateLoopingIterator.js
```js
import { LightningElement } from "lwc";
export default class TemplateLoopingIterator extends LightningElement {
  ceoList = [
    {
      id: 1,
      company: "Google",
      name: "Sundar Pichai"
    },
    {
      id: 2,
      company: "Apple Inc.",
      name: "Tim cook"
    },
    {
      id: 3,
      company: "Facebook",
      name: "Mark Zuckerberg"
    },
    {
      id: 4,
      company: "Amazon.com",
      name: "Jeff Bezos"
    },
    {
      id: 5,
      company: "Capgemini",
      name: "Paul Hermelin"
    }
  ];
}
```

File Name : templateLoopingIterator.html
```html
<template>
    <lightning-card title="Iterator loop demo" icon-name="custom:custom14">
      <ul class="slds-m-around_medium">
        <div class="list-group-inline">
          <template iterator:ceo={ceoList}>
            <div key={ceo.value.id}>
              <a
                href="#"
                if:true={ceo.first}
                class="list-group-item list-group-item-action header"
              >
                <strong>List of top companies and there CEO's : </strong>
              </a>
              <a href="#" class="list-group-item list-group-item-action">
                <strong>{ceo.value.company} : </strong>{ceo.value.name}
              </a>
              <a
                href="#"
                if:true={ceo.last}
                class="list-group-item list-group-item-action footer"
              >
                <strong>&copy; 2019 Lightning school salesforce </strong>
              </a>
            </div>
          </template>
        </div>
      </ul>
    </lightning-card>
  </template>
```

## Component Composition
Composition is Adding Component Within the body of another component
• Composition enables you to build complex components from simpler building-block components.

**How to refer child components name in parent components**
1. childComponent	&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;	&lt;c-child-component&gt;&lt;/c-child-component&gt;
2. childComponentDemo	&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;	&lt;c-child-component-demo&gt;&lt;/c-child-component-demo&gt;
3. sampleDemoLWC	&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;	&lt;c-sample-demo-l-w-c&gt;&lt;/c-sample-demo-l-w-c&gt;

_**Replace capital letter with small letter and prefixed with hyphen**_ <br/>
Try to avoid continuous capital letters in your component name.

## Accessing Elements in LWC
To access elements rendered by a component, use the template property. 
```js
this.template.querySelector (selector);
this.template.querySelectorAll (selector);
element. template.querySelectorAll (selector);
```
> **Note -** Don't use ID selector with querySelector

**lwc:dom="manual"** </br>
Add this directive to a native HTML element to attach an HTML element as a child.

## Parent to child Communication
Parent to child communication is always crucial for building a more significant and reusable component in a large application.

Let's understand how parent component pass string data to child component from the below fig
![parent-to-child-string](https://github.com/therishabh/salesforce-lwc/assets/7955435/eb5fd7df-0c3a-4416-b97a-e798963fce94)

### @api decorator

1. To make a field/property or method public, decorate it with @api decorator
2. When we want to expose the property we decorate the field with @api.
3. An owner component that uses the component in its HTML markup can access the component's public properties via HTML attributes. 
4. Public properties are reactive in nature and if the value of the property changes the component's template re-renders.

**Example**

**Parent component**
File Name : alertParentComponent.js
```js
import { LightningElement } from 'lwc';

export default class AlertParentComponent extends LightningElement {}
```

File Name : alertParentComponent.html
```html
<template>
    <div class="margin-bottom-2rem">
        <lightning-card title="Parent to child data communication using strings" icon-name="custom:custom14">
            <div class="slds-m-around_medium">
                <div>
                    <c-alert-child-component message="Indicates a dangerous or potentially negative action"></c-alert-child-component>
                    <c-alert-child-component class-name="success" message="Success! Indicates a successful or positive action.">
                    </c-alert-child-component>
                    <c-alert-child-component class-name="info" message="Info! Indicates a neutral informative change or action.">
                    </c-alert-child-component>
                    <c-alert-child-component class-name="warning" message="Warning! Indicates a warning that might need attention.">
                    </c-alert-child-component>
                </div>
            </div>
        </lightning-card>
    </div>
    
</template>
```

> Note - In Lightning Web Components we should conventionally use camelCase (lower case first letter, upper case subsequent words) to name the component and kebab-case (lower case words preceded with c- and spaced with '-' minus sign) when nesting the components in a composition scenario.

If your child public property is camelCase as in our case className, then we need to use the attribute as class-name in our child component calling

**Child component**
File Name : alertChildComponent.js
```js
import { LightningElement, api } from 'lwc';

export default class AlertChildComponent extends LightningElement {
    @api message
    @api className

    get alertClassName() {
        return this.className ? 'alert ' + this.className : 'alert'
    }
}
```

File Name : alertChildComponent.html
```html
<template>
    <div class={alertClassName}>
        {message}
    </div>
</template>
```

File Name : alertChildComponent.css
```css
.alert {
        padding: 20px;
        background-color: #f44336;
        color: white;
        opacity: 1;
        transition: opacity 0.6s;
        margin-bottom: 15px;
      }
      
.alert.success {background-color: #4CAF50;}
.alert.info {background-color: #2196F3;}
.alert.warning {background-color: #ff9800;}
```

## Parent to Child Communication by calling the Child method from the parent component

**Example**
**Parent component**

File Name : barParentComponent.js
```js
import { LightningElement } from 'lwc';

export default class BarParentComponent extends LightningElement {
    changeColor() {
        this.template.querySelector('c-bar-child-component').changeBarColor();
    }
}
```

File Name : barParentComponent.html
```html
<template>
    <div class="margin-bottom-2rem">
        <lightning-card title="Calling child method from parent" icon-name="custom:custom14">
            <div class="slds-m-around_medium">
                <div class="parent-wrapper">
                    <button class="btn" onclick={changeColor}>Click me to change bar color</button>
                    <div class="child-wrapper">
                        <c-bar-child-component></c-bar-child-component>
                    </div>
                </div>
            </div>
        </lightning-card>
    </div>
</template>
```

**Child component**
File Name : barChildComponent.js
```js
import { LightningElement, api } from 'lwc';

export default class BarChildComponent extends LightningElement {
    className = "greenBar";
    @api changeBarColor() {
        this.className = "redBar"
    }
}
```

File Name : barChildComponent.html
```html
 <template>
    <div class={className}>I am child component</div>
</template>
```

## Child to Parent Communication
There are Three kind of child to parent communication

1. Simple Event
2. Event With Data
3. Event Bubbling

**Example**
File Name : modalParentComponent.js
```js
import { LightningElement } from 'lwc';

export default class ModalParentComponent extends LightningElement {
    showModal = false
    showHandler() {
        this.showModal = true
    }
    modalCloseHandler(){
        this.showModal = false
    }
}
```

File Name : modalParentComponent.html
```html
<template>
    <lightning-card title="Simple Event" icon-name="custom:custom14">
        <div class="slds-var-m-around_medium">
            <button class="slds-button slds-button_success" onclick={showHandler}>Open Modal</button>
            <template if:true={showModal}>
                <c-modal-child-component
                header-text="Message!!"
                body-text="This Modal is a Child Component. Triggered from parent and on click of close button it will dispatch an event to parent handler"
                onclose={modalCloseHandler}
                ></c-modal-child-component>
            </template>
        </div>
    </lightning-card>
</template>
```

> Once close event get's triggered it gonna catch my the method modalCloseHandler which is map to the c-modal-child-component component onclose attribute.
> we are creating the custom event and passing the data by mapping it to **detail** property. Once event gets created we dispatch it to parent.
> Once parent recieve the event it will extract the data using **event.detail** and show the selectedPlayer on the screen


File Name : modalChildComponent.js
```js
import { LightningElement, api } from 'lwc';

export default class ModalChildComponent extends LightningElement {
    @api headerText
    @api bodyText
    closeHandler(){
        this.dispatchEvent(new CustomEvent('close'))
    }
}
```


File Name : modalChildComponent.html
```html
<template>
    <div id="myModal" class="modal">
        <div class="modal-content">
            <header>
                <strong>{headerText}</strong>
            </header>
            <p>{bodyText}</p>
            <footer class="text-right">
                <button class="btn danger" onclick={closeHandler}>Close</button>
            </footer>
        </div>
    </div>
</template>
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

## Slot
**Passing Markup into Slots**
1. Slot is useful to pass HTML markup into the another component.
2. &lt;slot&gt;&lt;/slot&gt; markup is used to catch the HTML passed by parent component
3. You can't pass an Aura component into a slot.
   
**There are two types of Slots**</br></br>
**Named Slots :** When name attribute is defined in slot element &lt;slot name="head"&gt;&lt;/slot&gt;</br>
**Unnamed Slots :** When a slot without a name attribute &lt;slot&gt;&lt;/slot&gt;</br>

**Example**

File Name : slotParentDemo.js
```js
import { LightningElement } from 'lwc';

export default class SlotParentDemo extends LightningElement {}
```

File Name : slotParentDemo.html
```html
<template>
    <lightning-card title="Slot Demos">
        <div class="slds-p-around_medium">
            <c-slot-child-demo>
                <p class="slds-text-color_success" slot="first">My Name is Salesforcetroop</p>
                <p class="slds-text-color_error" slot="second">My Age is 25</p>
                <p slot="footer"> I am footer</p>
            </c-slot-child-demo>
        </div>
        <div class="slds-p-around_medium">
            <c-slot-child-demo>
                <p class="slds-text-color_success" slot="first">My Name is Salesforcetroop</p>
                <p class="slds-text-color_error" slot="second">My Age is 25</p>
                <!-- <p slot="footer"> I am footer</p> -->
            </c-slot-child-demo>
        </div>
    </lightning-card>
</template>
```

File Name : slotChildDemo.js
```js
import { LightningElement } from 'lwc';

export default class SlotChildDemo extends LightningElement {
    handleFooterChange(){
        const footerElem = this.template.querySelector('.slds-card__footer')
        if(footerElem){
            footerElem.classList.remove('slds-hide')
        }
    }
}
```

File Name : slotChildDemo.html
```html
<template>
    <div>What is Your Name?</div>
    <div><slot name="first"></slot></div> <!--named slots-->
    <div>What is Your Age?</div>
    <div><slot name="second"></slot></div> 
    <footer class="slds-card__footer slds-hide">
        <slot name="footer" onslotchange={handleFooterChange}></slot>
    </footer>
</template>
```


## Create Static Resources
https://developer.salesforce.com/docs/platform/lwc/guide/create-resources.html

## How do you handle data security in Salesforce
https://www.apexhours.com/how-do-you-handle-data-security-in-salesforce/

## Salesforce Security Best Practices: Protecting Data and Ensuring Compliance
https://www.apexhours.com/salesforce-security-best-practices-protecting-data-and-ensuring-compliance/

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

## Navigation Service
The lightning/navigation service is used to navigate in Lightning Experience, Lightning Communities and in Salesforce Application. Navigation Service in Lightning Web Components are used to navigate to Record Pages, Web Pages, Objects, List Views, Custom Tabs, Related Lists, Files etc.

Navigation Service uses a PageReference rather than a URL. A PageReference is a JavaScript object that provides the details of Page Type, attributes and state of the Page.

The PageReference envelopes a component from future changes to URL formats. Page type(String) and attributes(Object) are required parameters, state(Object) is optional parameter. To use the navigation service in Lightning Web Components, first import it in the JavaScript file

```js
import { NavigationMixin } from 'lightning/navigation';
```

Next apply NavigationMixin function to component’s base class
```js
export default class SampleNavigationService extends NavigationMixin(LightningElement) {}
```

NavigateMixin adds two API’s to component’s class: </br>

**NavigateMixin.Navigate :** To navigate to another page in the application</br>
**NavigateMixin.GenerateURL :** To get a promise that resolves to the resulting URL. The URL can be used in the href attribute of an anchor. It can utilize the URL to open a new window using the Browser api – Window.open(url)</br>

**Examples**
#### Navigate to New Case record creation
```html
<!-- sampleNavigationService.html -->
<template>
    <lightning-card title="Navigation Service">
        <div class="slds-p-left_medium">
            <lightning-button label="New Case" onclick={navigateToNewCasePage}></lightning-button>
        </div>
    </lightning-card>
</template>
```

```js
import { LightningElement } from 'lwc';
import { NavigationMixin } from 'lightning/navigation';
 
export default class SampleNavigationService extends NavigationMixin(LightningElement) {
 
    navigateToNewCasePage() {
        this[NavigationMixin.Navigate]({
            type: 'standard__objectPage',
            attributes: {
                objectApiName: 'Case',
                actionName: 'new'
            },
        });
    }
}
```

#### Navigate to Case Home Page
```html
<template>
    <lightning-card title="Case Home Page Navigation">
        <div class="slds-p-left_medium">
            <a href={refUrl} onclick={handleNavigationClick}>Case Home</a>
        </div>
    </lightning-card>
</template>
```

```js
import { LightningElement, wire } from 'lwc';
import { NavigationMixin } from 'lightning/navigation';
 
export default class BasicNavigationLWC extends NavigationMixin(LightningElement) {
 
    refUrl;
 
    connectedCallback() {
        this.caseHomePageRef = {
            type: 'standard__objectPage',
            attributes: {
                objectApiName: 'Case',
                actionName: 'home'
            }
        };
        this[NavigationMixin.GenerateUrl](this.caseHomePageRef)
            .then(url => this.refUrl = url);
    }
 
    handleNavigationClick(evt) {
        evt.preventDefault();
        evt.stopPropagation();
        this[NavigationMixin.Navigate](this.caseHomePageRef);
    }
}
```

#### Navigation to record page
```js
navigateToViewCasePage() {
	this[NavigationMixin.Navigate]({
	    type: 'standard__recordPage',
	    attributes: {
		recordId: this.recId,
		objectApiName: 'Case',
		actionName: 'view'
	    },
	});
}
```

#### Navigation to custom application
```js
navigateToMyCustomApplication() {
	this[NavigationMixin.Navigate]({
	    type: 'standard__app',
	    attributes: {
		appTarget: 'c__MyCustomApplication',
	    }
	});
}
```

#### Navigation to external URL
```js
navigateToApexHoursPage() {
        this[NavigationMixin.Navigate]({
            type: 'standard__webPage',
            attributes: {
                url: 'https://www.apexhours.com/'
            }
        });
}
```

#### Navigation to custom tab
```js
navigateToCustomTab() {
        this[NavigationMixin.Navigate]({
            type: 'standard__navItemPage',
            attributes: {
                apiName: 'CustomTabName'
            },
        });
 }
```

#### Navigation to List View
```js
    navigateToCaseListView() {
        this[NavigationMixin.Navigate]({
            type: 'standard__objectPage',
            attributes: {
                objectApiName: 'Case',
                actionName: 'list'
            },
            state: {
                filterName: 'Recent'
            },
        });
    }
```

#### Navigation to Related List
```js
    navigateToContactRelatedList() {
        this[NavigationMixin.Navigate]({
            type: 'standard__recordRelationshipPage',
            attributes: {
                recordId: this.recordId,
                objectApiName: 'Account',
                relationshipApiName: 'Contacts',
                actionName: 'view'
            },
        });
    }
```

#### Navigation to Files
```js
    navToFilesPage() {
        this[NavigationMixin.Navigate]({
            type: 'standard__objectPage',
            attributes: {
                objectApiName: 'ContentDocument',
                actionName: 'home'
            },
        });
    }
```

#### Navigation to Tab
```js
    navigateToCustomTab() {
        this[NavigationMixin.Navigate]({
            type: 'standard__navItemPage',
            attributes: {
                apiName: 'CustomTabName'
            },
        });
    }
```


#### Navigation to Visualforce Page
```js
navigateToVisualForcePage() {
        this[NavigationMixin.GenerateUrl]({
            type: 'standard__webPage',
            attributes: {
                url: '/apex/CaseVFExample?id=' + this.recordId
            }
        }).then(generatedUrl => {
            window.open(generatedUrl);
        });
}
```

#### Navigation to Custom Aura Component
```js
openCustomLightningComponent(){
	this[NavigationMixin.Navigate]({
	    type: 'standard__component',
	    attributes: {
		componentName: 'c__AuraComponentName'
	    }
	});
}
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
    @wire(getPicklistvalues, { recordTypeId: '012000000000000AAA', fieldApiName: INDUSTRY_FIELD })
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
    @wire(getPicklistValuesByRecordType, { objectApiName: ACCOUNT_OBJECT })
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

Example
```js
import { LightningElement, wire, api } from 'lwc';
import {getRecord, getFieldValue, getFieldDisplayValue} from 'lightning/uiRecordApi'
import NAME_FIELD from '@salesforce/schema/Account.Name'
import OWNER_NAME_FIELD from '@salesforce/schema/Account.Owner.Name'
import ANNUAL_REVENUE_FIELD from '@salesforce/schema/Account.AnnualRevenue'
export default class GetRecordDemo extends LightningElement {
    name
    owner
    AnnualRevenue
    @api recordId
    @wire(getRecord, {recordId:'$recordId',
     fields:[NAME_FIELD, OWNER_NAME_FIELD, ANNUAL_REVENUE_FIELD]})
     accountHandler({data}){
         if(data){
             console.log(data)
             this.name = getFieldValue(data, NAME_FIELD) 
             this.AnnualRevenue = getFieldDisplayValue(data, ANNUAL_REVENUE_FIELD) 
             this.owner = getFieldValue(data, OWNER_NAME_FIELD) 

         }
     }
}
```

### getListInfoByName adapter
Use this wire adapter to get the metadata for a list view.

Syntax
```javascript
import { LightningElement, wire } from "lwc";
import { getListInfoByName } from "lightning/uiListsApi";
import ACCOUNT_OBJECT from "@salesforce/schema/Account";

export default class Example extends LightningElement {
  @wire(getListInfoByName, { objectApiName: ACCOUNT_OBJECT, listViewApiName: "AllAccounts" })
  propertyOrFunction;
}
```
**objectApiName —** (Required) The API name of a supported object.</br>
**listViewApiName —** (Required) The API name of a list view, such as **AllAccounts**.

**Example** </br>
File Name : getListInfoByNameDemo.js
```javascript
import { LightningElement, wire } from 'lwc';
import { getListInfoByName } from "lightning/uiListsApi";
import CASE_OBJECT from '@salesforce/schema/Case';
export default class GetListInfoByNameDemo extends LightningElement {
    error;
    displayColumns;
    @wire(getListInfoByName, {
      objectApiName: CASE_OBJECT.objectApiName,
      listViewApiName: "MyCases",
    })
    listInfo({ error, data }) {
      if (data) {
        console.log(data);
        this.displayColumns = data.displayColumns;
        this.error = undefined;
      } else if (error) {
        this.error = error;
        this.displayColumns = undefined;
      }
    }
}
```

File Name : getListInfoByNameDemo.html
```html
<template>
  <lightning-card title="getListInfoByName Demo">
    <div class="slds-p-around_medium">
      <template lwc:if={displayColumns}>
        <div class="slds-m-around_medium">
          <template for:each={displayColumns} for:item="col">
            <p key={col.fieldApiName}>{col.fieldApiName} : {col.label}</p>
          </template>
        </div>
      </template>
    </div>
  </lightning-card>
</template>
```

### createRecord
Creates a record.

Syntax
```js
import { createRecord } from 'lightning/uiRecordApi';
createRecord(recordInput: Record): Promise<Record>
```

**Example**
File Name : createRecordDemo.js
```js
import { LightningElement } from 'lwc';
import {createRecord} from 'lightning/uiRecordApi'
import CONTACT_OBJECT from '@salesforce/schema/Contact'
import { ShowToastEvent } from 'lightning/platformShowToastEvent';
export default class CreateRecordDemo extends LightningElement {
    formFields={}
    changeHandler(event){
        const {name, value} = event.target
        this.formFields[name]=value
    }
    createContact(){
        const recordInput = {apiName:CONTACT_OBJECT.objectApiName, fields:this.formFields}
        createRecord(recordInput).then(result=>{
            this.showToast('Success!!', `contact created with is ${result.id}`)
            this.template.querySelector('form.createForm').reset()
            this.formFields={}
        }).catch(error=>{
            this.showToast('Error Creating record', error.body.message, 'error')
        })
    }

    showToast(title, message, variant){
        this.dispatchEvent(new ShowToastEvent({
            title,
            message,
            variant:variant || 'success'
        }))
    }
}
```

File Name : createRecordDemo.html
```html
<template>
    <lightning-card title="create record form demo">
        <div class="slds-p-around_medium">
            <form class="createForm">
                <lightning-input label="First Name" name="FirstName"
                 onchange={changeHandler} class="slds-m-bottom_x-small"></lightning-input>
                 <lightning-input label="Last Name" name="LastName"
                 onchange={changeHandler} class="slds-m-bottom_x-small"></lightning-input>
                 <lightning-input label="Title" name="Title"
                 onchange={changeHandler} class="slds-m-bottom_x-small"></lightning-input>
                 <lightning-input type="tel" label="Phone" name="Phone"
                 onchange={changeHandler} class="slds-m-bottom_x-small"></lightning-input>
                 <lightning-input type="email" label="Email" name="Email"
                 onchange={changeHandler} class="slds-m-bottom_x-small"></lightning-input>
                 <lightning-button label="Create Contact" variant="brand" onclick={createContact}></lightning-button>
            </form>
        </div>
    </lightning-card>
</template>
```



## Apex In LWC
### Expose Apex Methods to LWC
1. Apex Method must be static and either global or public
2. Method should be annotated with @AuraEnabled
   
**Syntax**
```js
public with sharing class AccountController {
	@AuraEnabled(cacheable=true)
	public static List<Account> getAccountList() {
		return [SELECT Id, Name, Type, Industry from Account];
	}
｝
```

**Example** </br>
File Name : AccountController.cls
```java
public with sharing class AccountController {
    
    @AuraEnabled(cacheable=true)
    public static List<Account> getAccountList(){
        return [SELECT Id, Name, Type, Industry from Account LIMIT 5];
    }
}
```

### Import Apex Methods
Use default import syntax in JavaScript to import an Apex method via the @salesforce/apex scoped packages.

**Syntax**
```js
import apexMethodName from "@salesforce/apex/Namespace.Classname.apexMethodReference';
```

**apexMethodName —** A symbol that identifies the Apex method. </br>
**apexMethodReference —** The name of the Apex method to import.</br>
**Classname —** The name of the Apex class.</br>
**Namespace —** lf the class is in the same namespace as the component, don't specify a namespace. If the class is in a managed package, specify the namespace of the managed package.

**Example** </br>
```js
import { LightningElement } from 'lwc';
import getAccountList from '@salesforce/apex/AccountController.getAccountList';

export default class ApexWireDemo extends LightningElement {
    
}
```

### Wire Apex Method
```js
import { LightningElement, wire } from 'lwc';
import getAccountList from '@salesforce/apex/AccountController.getAccountList'
export default class ApexWireDemo extends LightningElement {
    accountList
    
    @wire(getAccountList)
    accounts

    
    @wire(getAccountList)
    accountsHandler({data, error}){
        if(data){
            this.accountList = data.map(item=>{
                let newType = item.Type === 'Customer - Channel' ? 'Channel':
                item.Type === 'Customer - Direct' ? 'Direct':'-------'
                return {...item, newType}
            })
        }
        if(error){
            console.error(error)
        }
    }
}
```

```html
<template>
    <lightning-card title="Apex Wire to Property Demo">
        <div class="slds-p-around_medium">
            <template if:true={accounts.data}>
                <template for:each={accounts.data} for:item="account">
                    <div class="slds-box sldx-box_xx-small" key={account.Id}>
                       <p><strong>Name : </strong>{account.Name}</p>
                       <p><strong>Type : </strong>{account.Type}</p>
                       <p><strong>Industry : </strong>{account.Industry}</p>
                    </div>
                </template>
            </template>
        </div>
    </lightning-card>

    <div class="slds-m-top_medium"></div>

    <lightning-card title="Apex Wire To Function Demo">
        <div class="slds-p-around_medium">
            <template if:true={accountList}>
                <template for:each={accountList} for:item="account">
                    <div class="slds-box slds-box_xx-small" key={account.Id}>
                        <p><strong>Name : </strong> {account.Name}</p>
                        <p><strong>Type : </strong> {account.newType}</p>
                        <p><strong>Industry : </strong> {account.Industry}</p>
                    </div>
                </template>
               
            </template>
        </div>
    </lightning-card>

</template>
```

### Wire Apex Method with Parameters

File Name : AccountController.cls
```java
public with sharing class AccountController {
    @AuraEnabled(cacheable=true)
    public static List<Account> getAccountList(String type){
        return [SELECT Id, Name, Type, Industry from Account WHERE Type:type LIMIT 5];
    }
}
```

File Name : wireApexWithParams.js
```js
import { LightningElement, wire } from 'lwc';
import filterAccountType from '@salesforce/apex/AccountController.filterAccountType'
export default class WireApexWithParams extends LightningElement {
    selectedType=''
    @wire(filterAccountType, {type:'$selectedType'})
    filteredAccounts

    get typeOptions(){
        return [
            {label:"Customer - Channel", value:"Customer - Channel"},
            {label:"Customer - Direct", value:"Customer - Direct"}
        ]
    }
    typeHandler(event){
        this.selectedType = event.target.value
    }
}
```

File Name : wireApexWithParams.html
```html
<template>
    <lightning-card title="Apex Wire Demo with params">
        <div class="slds-var-p-around_medium">
            <lightning-combobox
                name="type"
                lable="Choose your Type"
                value={selectedType}
                options={typeOptions}
                onchange={typeHandler}
            ></lightning-combobox>
            <template if:true={filteredAccounts.data}>
                <template for:each={filteredAccounts.data} for:item="account">
                    <div class="slds-box slds-box_xx-small" key={account.Id}>
                        <p><strong>Name:</strong> {account.Name}</p>
                        <p><strong>Type:</strong> {account.Type}</p>
                    </div>
                </template>
            </template>
        </div>
    </lightning-card>
</template>
```

### Call Apex Methods Imperatively (with and without Parameters)

Use this approach over @wire in the following situations
1) To call a method that isn't annotated with **cacheable=true**, which includes any method that inserts, updates, or deletes data.
2) To control when the invocation occurs.
3) To work with objects that aren't _supported by User Interface API_, like Task and Event.
4) To call a method from an ES6 module that doesn't extend LightningElement

File Name : AccountController.cls
```java
public with sharing class AccountController {
    @AuraEnabled(cacheable=true)
    public static List<Account> getAccountList(){
        return [SELECT Id, Name, Type, Industry from Account LIMIT 5];
    }

    @AuraEnabled(cacheable=true)
    public static List<Account> filterAccountType(String type){
        return [SELECT Id, Name, Type from Account where Type=:type LIMIT 5];
    }

    @AuraEnabled(cacheable=true)
    public static List<Account> findAccounts(String searchKey){
        String key = '%' + searchKey + '%';
        return [SELECT Id, Name, Type, Industry FROM Account WHERE Name LIKE :key LIMIT 5];
    }
}
```

File Name : apexImperativeWithParamsDemo.js
```js
import { LightningElement } from 'lwc';
import findAccounts from '@salesforce/apex/AccountController.findAccounts'
export default class ApexImperativeWithParamsDemo extends LightningElement {
    searchKey=''
    accounts
    timer
    searchHandler(event){
        window.clearTimeout(this.timer)
        this.searchKey = event.target.value
        this.timer = setTimeout(()=>{
            this.callApex()
        }, 1000);
    }

    callApex(){
        findAccounts({searchKey:this.searchKey})
        .then(result=>{
            this.accounts = result
        }).catch(error=>{
            console.error(error)
        })
    }
}
```

File Name : apexImperativeWithParamsDemo.html
```html
<template>
    <lightning-card title="Apex imperative with params demo">
        <div class="slds-p-around_medium">
            <lightning-input
            type="search"
            onchange={searchHandler}
            label="Search Account"
            value={searchKey}
            ></lightning-input>
        </div>

        <template if:true={accounts}>
            <template for:each={accounts} for:item="account">
                <div class="slds-box slds-box_xx-small" key={account.Id}>
                    <p>Name - {account.Name}</p>
                    <p>Type - {account.Type}</p>
                    <p>Industry - {account.Industry}</p>
                </div>
            </template>
        </template>

    </lightning-card>
</template>
```



















