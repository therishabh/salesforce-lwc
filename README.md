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
15. [Child to Parent Communication](#child-to-parent-communication)
16. [Setter Method](#setter-method)
17. [Lifecycle Hooks](#lifecycle-hooks)
18. [Slot](#slot)
19. [Create Static Resources](#create-static-resources)
20. [Internationalization](#internationalization)
21. [Navigation Service](#navigation-service)
	- [Navigate to New Case record creation](#navigate-to-new-case-record-creation)
	- [Navigate to Case Home Page](#navigate-to-case-home-page)
	- [Navigation to record page](##navigation-to-record-page)
	- [Navigation to custom application](#navigation-to-custom-application)
	- [Navigation to external URL](#navigation-to-external-url)
	- [Navigation to custom tab](#navigation-to-custom-tab)
 	- [Navigation to named page](#navigation-to-named-page)  
	- [Navigation to List View](#navigation-to-list-view)
	- [Navigation to Related List](#navigation-to-related-list)
	- [Navigation to Files](#navigation-to-files)
	- [Navigation to Tab](#navigation-to-tab)
	- [Navigation to Visualforce Page](#navigation-to-visualforce-page)
	- [Navigation to Custom Aura Component](#navigation-to-custom-aura-component)
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
26. [Flow to LWC data Transfer](#flow-to-lwc-data-transfer)
27. [LWC to Flow data Transfer](#lwc-to-flow-data-transfer)
28. [Component Communication](#component-communication)
    - [PubSub](#pubsub)
    - [Lightning Messaging Service](#lightning-messaging-service)

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

# @track

**🔥 Quick Points (Interview Notes)**

👉 `@track` is a decorator used to make **properties reactive (especially objects & arrays)**
👉 It ensures UI updates when **nested values change**
👉 In **modern LWC (latest versions)**, simple properties are **reactive by default**
👉 `@track` is mainly needed for **deep changes inside objects/arrays**
👉 Without `@track`, LWC tracks only **reference changes**, not internal mutations
👉 Overuse of `@track` is **not recommended**
👉 It is **not needed for primitive types** (string, number, boolean)

---

**🧠 1. What is `@track`?**

> `@track` makes a property **fully reactive**, including its **internal fields**

Meaning:

* If object/array ke **andar ka value change ho**, UI update ho jaye

---

#### ⚙️ 2. Basic Example

**❌ Without `@track`**

```js
user = { name: 'Rishabh' };

changeName() {
    this.user.name = 'Rahul'; // ❌ UI may NOT update
}
```

---

**✅ With `@track`**

```js
import { LightningElement, track } from 'lwc';

export default class TrackDemo extends LightningElement {

    @track user = { name: 'Rishabh' };

    changeName() {
        this.user.name = 'Rahul'; // ✅ UI updates
    }
}
```

---

#### 🔁 3. Array Example

**❌ Without `@track`**

```js
items = ['A', 'B'];

addItem() {
    this.items.push('C'); // ❌ UI may not update
}
```

---

**✅ With `@track`**

```js
@track items = ['A', 'B'];

addItem() {
    this.items.push('C'); // ✅ UI updates
}
```

---

**⚡ 4. Modern Best Practice (Important)**

👉 In latest LWC, instead of using `@track`, we usually use **immutable update pattern**

**✔ Recommended way**

```js
items = ['A', 'B'];

addItem() {
    this.items = [...this.items, 'C']; // ✅ UI updates without @track
}
```

👉 Because reference change ho raha hai

---

**🧩 5. When `@track` is Required?**

Use `@track` when:

- ✔ Complex object ho
- ✔ Deep nested property change ho
- ✔ Direct mutation kar rahe ho

Example:

```js
@track user = {
    name: 'Rishabh',
    address: {
        city: 'Delhi'
    }
};

updateCity() {
    this.user.address.city = 'Noida'; // needs @track
}
```

---

**❌ When NOT to use `@track`**

Do NOT use `@track` for:

```js
name = 'Rishabh'; // primitive → already reactive
```

```js
this.name = 'Rahul'; // works without @track
```

---

#### 🎤 Interview Ready Answer

> `@track` in LWC is used to make properties reactive for internal mutations of objects and arrays. In modern LWC, simple properties are reactive by default, and for arrays/objects we usually use immutable updates instead of `@track`.

---
---

# Conditional Rendering

> **Condition ke basis par HTML ko show / hide karna**

Matlab:

* Agar condition **true** → HTML dikhega
* Agar condition **false** → HTML hide ho jayega

---

## 🔹 LWC me Conditional Rendering ke 2 tareeke

### 1️⃣ `if:true` / `if:false`  ✅ (MOST USED)

### 2️⃣ `<template if:true>` & `<template if:false>`

---

## 🔹 Example 1: Simple Boolean Condition

### JS

```js
import { LightningElement } from 'lwc';

export default class ConditionalDemo extends LightningElement {
    showMessage = false;

    toggleMessage() {
        this.showMessage = !this.showMessage;
    }
}
```

### HTML

```html
<template>
    <lightning-button label="Toggle" onclick={toggleMessage}></lightning-button>

    <template if:true={showMessage}>
        <p>🎉 Message is visible</p>
    </template>

    <template if:false={showMessage}>
        <p>❌ Message is hidden</p>
    </template>
</template>
```

---

## 🔹 Example 2: `if:true` directly on element

```html
<template>
    <p if:true={showMessage}>Hello User 👋</p>
    <p if:false={showMessage}>Bye User 👋</p>
</template>
```

📌 **Rule:**

* Ek hi element par **`if:true` ya `if:false`** lag sakta hai
* Dono ek saath ❌

---

## 🔹 Example 3: Login / Logout Scenario (Real Use Case)

### JS

```js
export default class LoginStatus extends LightningElement {
    isLoggedIn = false;

    login() {
        this.isLoggedIn = true;
    }

    logout() {
        this.isLoggedIn = false;
    }
}
```

### HTML

```html
<template>
    <template if:true={isLoggedIn}>
        <p>Welcome User 😊</p>
        <lightning-button label="Logout" onclick={logout}></lightning-button>
    </template>

    <template if:false={isLoggedIn}>
        <p>Please Login 😐</p>
        <lightning-button label="Login" onclick={login}></lightning-button>
    </template>
</template>
```

---

## 🔹 Example 4: Conditional Rendering with Object Data

### JS

```js
import { LightningElement, track } from 'lwc';

export default class UserCard extends LightningElement {
    @track user = {
        name: 'Amit',
        isAdmin: true
    };
}
```

### HTML

```html
<template>
    <p>Name: {user.name}</p>

    <template if:true={user.isAdmin}>
        <p>👑 Admin Access Granted</p>
    </template>

    <template if:false={user.isAdmin}>
        <p>🚫 Normal User</p>
    </template>
</template>
```

---

## 🔹 Example 5: Multiple Conditions (getter use karo) ⭐

❌ Direct comparison allowed nahi hoti:

```html
<!-- WRONG -->
<template if:true={age > 18}>
```

✅ **Correct way: getter**

### JS

```js
export default class AgeCheck extends LightningElement {
    age = 20;

    get isAdult() {
        return this.age >= 18;
    }
}
```

### HTML

```html
<template>
    <template if:true={isAdult}>
        <p>Adult ✅</p>
    </template>

    <template if:false={isAdult}>
        <p>Minor ❌</p>
    </template>
</template>
```

---

## 🔹 Important Rules (Interview GOLD ⭐)

✔ LWC HTML me **expressions allowed nahi**
✔ Always use **boolean variable / getter**
✔ `if:true` / `if:false` sirf **HTML ke liye**
✔ JavaScript logic → **JS file me**

---

## 🔹 Common Mistakes ❌

* `{age > 18}` directly HTML me likhna
* String `"true"` ko boolean samajhna
* Same element pe `if:true` & `if:false` dono lagana

---

## 🔹 One-Line Summary

> **LWC me conditional rendering ka matlab hai: JS me condition banao → HTML me `if:true / if:false` se show-hide karo**


# 🔹 1️⃣ `if:true / if:false` (OLD STYLE)

### Example

```html
<template>
    <template if:true={isVisible}>
        <p>Hello</p>
    </template>

    <template if:false={isVisible}>
        <p>Bye</p>
    </template>
</template>
```

### ✅ Pros

* Simple
* Easy to understand
* Aaj bhi kaam karta hai

### ❌ Cons

* `else if` directly nahi
* Multiple `<template>` likhne padte
* Readability kam ho jaati hai

---

# 🔹 2️⃣ `lwc:if / lwc:elseif / lwc:else` (NEW STYLE ⭐)

🔥 **Salesforce ne ye syntax introduce kiya** taaki code clean ho.

### Example (Exactly tum jo bole)

```html
<template>
    <template lwc:if={isVisible}>
        <p>Visible Content</p>
    </template>

    <template lwc:elseif={checkJapanText}>
        <p>Japan Text 🇯🇵</p>
    </template>

    <template lwc:else>
        <p>Default Text</p>
    </template>
</template>
```

### ✅ Pros

* Clean & readable
* Proper **if / else if / else**
* Interview me **ye bolo to impression padta hai 😄**
* Best for **multiple conditions**

### ❌ Rules (IMPORTANT)

* `lwc:elseif` ke baad **condition required**
* `lwc:else` ke saath **koi condition nahi hoti**
* Sab `<template>` **continuous hone chahiye**
* Beech me koi HTML nahi

❌ WRONG:

```html
<template lwc:if={a}></template>
<p>break</p>
<template lwc:else></template>
```

---

# 🔹 3️⃣ Same Example using both (Comparison)

### OLD WAY

```html
<template if:true={isAdmin}>
    <p>Admin</p>
</template>

<template if:false={isAdmin}>
    <p>User</p>
</template>
```

### NEW WAY ⭐

```html
<template lwc:if={isAdmin}>
    <p>Admin</p>
</template>
<template lwc:else>
    <p>User</p>
</template>
```

---

# 🔹 4️⃣ Kab kya use karein? (REAL PROJECT ADVICE)

| Situation           | Best Choice                      |
| ------------------- | -------------------------------- |
| Simple true/false   | `lwc:if / lwc:else`              |
| Multiple conditions | `lwc:if / lwc:elseif / lwc:else` |
| Old project         | `if:true / if:false`             |
| New project         | ⭐ `lwc:*`                        |

---

### 🔹 5️⃣ Interview Answer (ONE-LINER ⭐)

> “Earlier LWC used `if:true / if:false`, but now Salesforce recommends `lwc:if`, `lwc:elseif`, and `lwc:else` for cleaner and more readable conditional rendering.”

---

# 🔹 6️⃣ Common Mistake ❌

❌ `lwc:else={condition}`
✅ `lwc:else` (no condition)

Tum jo likh rahe the:

```html
lwc:else={checkJapanText} ❌
```

Correct:

```html
lwc:else ✅
```

---






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

# Parent to child Communication

In Lightning Web Components, a **parent component sends data or calls methods on a child component using `@api`**.

There are **2 main ways**:

1️⃣ **Pass data via public property (`@api`)**
2️⃣ **Call child’s public method (`@api`)**

```
Parent Component ──▶ Child Component
```

---

**🧩 Example Scenario**

* Parent has a button
* Parent sends a **message** to child
* Child displays that message

---

## 🟦 1) Passing Data via Public Property (`@api`)

## 👉 Child Component

### childComponent.js

```js
import { LightningElement, api } from 'lwc';

export default class ChildComponent extends LightningElement {
    @api message; // public property from parent
}
```

---

### childComponent.html

```html
<template>
    <p>Message from Parent: {message}</p>
</template>
```

---

## 👉 Parent Component

### parentComponent.js

```js
import { LightningElement } from 'lwc';

export default class ParentComponent extends LightningElement {
    parentMessage = 'Hello from Parent Component';
}
```

---

### parentComponent.html

```html
<template>
    <c-child-component message={parentMessage}></c-child-component>
</template>
```

---

### ✅ Output

Child UI will show:

```
Message from Parent: Hello from Parent Component
```

---

## 🟩 2) Calling Child Method from Parent

👉 Sometimes parent needs to **trigger an action in child**

---

## 👉 Child Component

### childComponent.js

```js
import { LightningElement, api } from 'lwc';

export default class ChildComponent extends LightningElement {

    @api
    showAlert() {
        alert('Child method called from Parent!');
    }
}
```

---

## 👉 Parent Component

### parentComponent.html

```html
<template>
    <lightning-button
        label="Call Child Method"
        onclick={handleClick}>
    </lightning-button>

    <c-child-component></c-child-component>
</template>
```

---

### parentComponent.js

```js
import { LightningElement } from 'lwc';

export default class ParentComponent extends LightningElement {

    handleClick() {
        const child = this.template.querySelector('c-child-component');
        child.showAlert(); // calling child method
    }
}
```

---

### 🎯 What Happens

👉 Button click in parent →
👉 Parent finds child using `querySelector` →
👉 Calls `@api` method →
👉 Child executes method

---

## ⚡ Important Rules (Interview Must)

### 🔹 1. Use `@api` for public access

```js
@api property;
@api method() {}
```

---

### 🔹 2. Data binding is **reactive**

Agar parent value change kare:

```js
this.parentMessage = 'Updated Message';
```

👉 child UI automatically update ho jayega

---

### 🔹 3. `querySelector` returns first matching child

Agar multiple child components ho to:

```js
this.template.querySelectorAll('c-child-component')
```

---

#### 🎤 Interview Ready Answer

> In LWC, parent-to-child communication is achieved using the `@api` decorator. The parent can pass data to the child via public properties, and it can also call public methods defined in the child component using `this.template.querySelector()`.

---

# Child to Parent Communication

In Lightning Web Components, **a child component communicates with its parent by dispatching a CustomEvent**.
The parent listens to that event using the **`on<eventname>`** handler in its template.

```
Child Component ──(dispatchEvent)──▶ Parent Component
```

---

## 🧩 Example Scenario

* The **child** has a button.
* When clicked, it sends some data (e.g., a name or record Id) to the **parent**.
* The **parent** receives that data and handles it.

---

## 🟦 1) Child Component

### childComponent.html

```html
<template>
    <lightning-button
        label="Send Data to Parent"
        onclick={handleClick}>
    </lightning-button>
</template>
```

### childComponent.js

```js
import { LightningElement } from 'lwc';

export default class ChildComponent extends LightningElement {

    handleClick() {
        const payload = {
            name: 'Rishabh',
            action: 'clicked'
        };

        // Create custom event (name should be lowercase)
        const evt = new CustomEvent('senddata', {
            detail: payload
        });

        // Dispatch to parent
        this.dispatchEvent(evt);
    }
}
```

---

## 🟩 2) Parent Component

### parentComponent.html

```html
<template>
    <c-child-component onsenddata={handleChildData}></c-child-component>
</template>
```

> Note: `onsenddata` corresponds to the child’s event name `senddata`.

---

### parentComponent.js

```js
import { LightningElement } from 'lwc';

export default class ParentComponent extends LightningElement {

    handleChildData(event) {
        const dataFromChild = event.detail;

        console.log('Received from child:', dataFromChild);

        // You can now use this data (update UI, call Apex, etc.)
    }
}
```

---

### ✅ What Happens

When the button in the **child** is clicked:

* The child dispatches `senddata` with `detail`.
* The parent’s `handleChildData` is invoked.
* `event.detail` contains the payload.

Console output:

```
Received from child: { name: 'Rishabh', action: 'clicked' }
```

---

#### ⚡ Key Rules (Important for Interviews)

1. **Event name must be lowercase**

   ```js
   new CustomEvent('senddata') // ✅
   ```

2. **Data is always passed via `detail`**

   ```js
   new CustomEvent('senddata', { detail: payload })
   ```

3. **Parent listens using `on<eventname>`**

   ```html
   <c-child-component onsenddata={handleChildData}></c-child-component>
   ```

---

## 🚀 Passing Record Id (Common Real Use Case)

### Child

```js
handleSelect(event) {
    const recordId = event.target.dataset.id;

    this.dispatchEvent(
        new CustomEvent('select', { detail: recordId })
    );
}
```

### Parent

```html
<c-child-component onselect={handleSelectRecord}></c-child-component>
```

```js
handleSelectRecord(event) {
    console.log('Selected record Id:', event.detail);
}
```

---

#### ⭐ Advanced Tip (Cross Shadow DOM)

If you need the event to bubble up through multiple levels:

```js
new CustomEvent('senddata', {
    detail: payload,
    bubbles: true,
    composed: true
});
```

---

### 🎤 Interview-Ready Answer

> In LWC, child-to-parent communication is done using Custom Events. The child dispatches an event using `this.dispatchEvent(new CustomEvent('eventname', { detail }))`, and the parent listens to it in the template using `on<eventname>={handler}` to receive the data from `event.detail`.


### 🆚 Parent → Child vs Child → Parent

| Direction      | Technique                |
| -------------- | ------------------------ |
| Parent → Child | `@api` property / method |
| Child → Parent | `CustomEvent`            |
| Unrelated      | LMS / PubSub             |

---
---


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

## Lifecycle Hooks
Lifecycle Hooks in Lightning Web Component can be considered as a callback method that is triggered at a particular phase of a component instance’s lifecycle.
Lifecycle hooks are special methods or functions that are automatically called at specific stages of a component’s life in a web application.

Here’s a brief overview of some essential lifecycle hooks:

**constructor():** This is where the component is initialized. You can set default values and perform one-time setup.</br>
**connectedCallback():** After the component is added to the DOM, this hook runs. It’s a great place to perform DOM manipulations and data retrieval.</br>
**renderedCallback():** This hook is triggered after rendering occurs. It’s ideal for operations that require knowledge of the rendered DOM.</br>
**disconnectedCallback():** When the component is removed from the DOM, this hook is invoked. Use it for cleanup operations and resource releases.</br>
**errorCallback():** If an error occurs during rendering, this hook is called. It’s your opportunity to gracefully handle errors.</br>

**Flow of Lifecycle hooks**</br>
First it called parent constructor then parent connectedCallBack and then if there is any child component then it moves to child constructor → connectedCall Back → renderedCallBack then it moves to parent renderedCallback</br>
![image](https://github.com/therishabh/salesforce-lwc/assets/7955435/f28ee98b-47a5-49cc-9ee7-d95254425b60)


1. Creation:

`constructor()`: This is the first hook to run when an instance of the component is created. It’s where you initialize variables and set default values.

**constructor()**

1. Invoked when the **instance of the component is created** (similar to init() in aura).
2. Fired in the parent component first since it **flows from parent to child**.
3. You have to **call super() inside first** to call parent class constructor ie. LightningElement.
4. Access element in the component template, **use this.template**.

```js
import { LightningElement } from 'lwc';
 
export default class LifeCycleHookParent extends LightningElement {
  constructor() {
    super(); // call LightningElement class constructor console.log('Parent Constructor Called');
    let con = this.template //access host element
    console.log(con);
  }
}
```

2. Initialization:

`connectedCallback()`: After the component is initialized, this hook is called. It’s an ideal place for DOM manipulations and data retrieval.

**connectedCallback()**

1. Invoke when **component inserted into DOM**.
2. It flows **Parent to Child**.
3. Used for to **perform initialisation task** such as fetch data, set up cache, listen events.
4. To check component is **connected** in DOM, use isConnected method.

```js
connectedCallback(){
  console.log('Parent Connected Call Back called');
  let cb = this.template
  console.log('is connected=> ' + cb.isConnected);
}
```

3. Rendering:

`renderedCallback()`: This hook is triggered after the component’s initial render. It’s suitable for actions that require knowledge of the rendered DOM, like interacting with elements.

**renderedCallback()**

1. Use it to perform logic after a component has finished the rendering phase. **It invoked when a component is completely rendered on UI.**
2. Flows from **child to parent** component.
3. Component rendered many times during there lifecycle, **to track renderedCallBack(), use isRendered boolean field.**
4. Property **leads to infinite loop** in renderedCallBack().

```js
import { LightningElement } from 'lwc';
export default class LifeCycleHookParent extends LightningElement {
  isRendered = true // to check component is rendered
  renderedCallback() {
    if (this.isRendered) {
      console.log('Parent Rendered call Back called');
      this.isRendered = false
    }
  ?
 }
```

4. Reactivity:

Whenever a property or variable changes in the component, it may trigger a reactivity cycle. During this cycle, the component checks for changes in properties, and if changes are detected, it re-renders and invokes the **`renderedCallback`** again.

5. Destruction:

`disconnectedCallback()`: When the component is removed from the DOM, this hook is called. It’s an excellent place for cleanup operations and releasing resources like event listeners.

**disconnectedCallback()**

- Called when the element is **removed from a documen**t (remove event listener, remove time interval etc).
- Follows **Parent to Child.**
- Use disconnectedCallback() **to clean up work done in the connectedCallback()**, like removing event listeners.
- You can also use this hook to **unsubscribe message channel.** </br>

6. Error Handling:

`errorCallback()`: If an error occurs during rendering, this hook is invoked. It provides an opportunity to gracefully handle errors and display appropriate messages.

**errorCallback()**

Implement it to create an error boundary component that captures errors in all the descendent components in its tree.

It captures errors that occur in the descendant’s lifecycle hooks or during an event handler declared in an HTML template.

1. Called when a descendant(Child) component throws an error.
2. Two arguments are passed in errorCallback(error,stack), the error argument is a JavaScript native error object, and the stack argument is a string.

```js
errorCallback(error, stack){
  console.log(error message);
  console.log('Stack: - ' + stack);
}
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

#### Navigation to named page
```js
import { LightningElement } from 'lwc';
import { NavigationMixin } from 'lightning/navigation';

export default class NavigateToPage extends NavigationMixin(LightningElement) {
    navigateToPage() {
        // Navigation to a standard named page
        this[NavigationMixin.Navigate]({
            type: 'standard__namedPage',
            attributes: {
                pageName: 'home'
            }
        });
    }
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





















## Lightning Data Service
Lightning Data Service is a centralized data caching mechanism which is utilized to perform create, read, update or delete on a record without having a server side apex call in Lightning web components.

https://developer.salesforce.com/docs/platform/lwc/guide/data-ui-api.html

![Screenshot Capture - 2024-05-05 - 19-01-36](https://github.com/therishabh/salesforce-lwc/assets/7955435/25ef2090-c02f-4a08-9390-3b0eb9f6de3c)

### Advantages of Lightning Data Service



## Base Lightning Components
### Introduction to Work With Data In LWC
There are many ways of interacting with Salesforce data in the Lightning web components. Knowing which approach to use for a particular use case helps you to write less code, easier code, and code that is more maintainable. The efficiency of your components is improved by using the best solution for each situation.

![Screenshot Capture - 2024-05-05 - 18-58-24](https://github.com/therishabh/salesforce-lwc/assets/7955435/b7dbe4e8-4133-4b16-9679-867bbee91b14)


### Base Lightning Components
Base Lightning Components are built on Lightning Data Service. So, Lightning Data Service is used behind the scenes by base components and inherits its caching and synchronisation capabilities

Below are the 3 base lightning components build on Lightning Data Service:

**1. lightning-record-form:** A form with standard lightning UI to create, view or edit a record
**2. lightning-record-edit-form:** A form to create record with specified fields or update fields in an existing record
**3. lightning-record-view-form:** A form to display specific fields data of a record in read-only mode


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

## Flow to LWC data Transfer
commuteFlowToLWC.html
```html
<template>
    <lightning-input label="Address" value={myname}></lightning-input> 
</template>
```

CommuteFlowToLWC.js
```js
import { LightningElement, api } from 'lwc';

export default class CommuteFlowToLWC extends LightningElement {
    name;

    connectedCallback() {
        console.log(this.myname);
    }

    @api
    get myname() {
        return this.name;
    }
    set myname(data) {
        this.name = data.toUpperCase() + ' bansal';
    }
}
```

commuteFlowToLWC.js-meta.xml
```xml
<?xml version="1.0" encoding="UTF-8"?>
<LightningComponentBundle xmlns="http://soap.sforce.com/2006/04/metadata">
    <apiVersion>59.0</apiVersion>
    <isExposed>true</isExposed>
    <targets>
        <target>lightning__FlowScreen</target>
    </targets>
    <targetConfigs>
        <targetConfig targets="lightning__FlowScreen">
            <property name="myname" type="String" label="Shikha Input"  />
        </targetConfig>

    </targetConfigs>
</LightningComponentBundle>
```

#### Create Screen Flow – Flow To LWC Communication
- Create a Screen flow and name it Flow to Lightning Web Component Communication
![image](https://github.com/therishabh/salesforce-lwc/assets/7955435/d10b225e-a65e-40be-9aa3-07d39b20ed5e)

- Add a text input element and provide Label/Api name
![image](https://github.com/therishabh/salesforce-lwc/assets/7955435/d06b7eeb-a3c1-4401-9046-f34b596bea25)

- Add the Lightning Web Component on Screen you created previously and pass text input element value to it
![image](https://github.com/therishabh/salesforce-lwc/assets/7955435/0ac5f1ff-0be4-4288-aaba-7e0aa8dcb71a)


## LWC to Flow data Transfer
commuteLWCToFlow.html
```html
<template>
    <lightning-input label="Email" type="email" onchange={getEmail}></lightning-input>
</template>
```

commuteLWCToFlow.js
```js
import { LightningElement, api } from 'lwc';
import {FlowAttributeChangeEvent} from 'lightning/flowSupport';

export default class CommuteLWCToFlow extends LightningElement {
    @api email;

    getEmail(event){
        // eslint-disable-next-line @lwc/lwc/no-api-reassignments
        this.email = event.target.value;
        this.dispatchEvent(new FlowAttributeChangeEvent('email', this.email))
    }
}
```

commuteLWCToFlow.js-meta.xml
```xml
<?xml version="1.0" encoding="UTF-8"?>
<LightningComponentBundle xmlns="http://soap.sforce.com/2006/04/metadata">
    <apiVersion>59.0</apiVersion>
    <isExposed>true</isExposed>
    <targets>
        <target>lightning__FlowScreen</target>
    </targets>
    <targetConfigs>
        <targetConfig targets="lightning__FlowScreen">
            <property name="email" type="String" label="Email Input" role="outputOnly" />
        </targetConfig>
    </targetConfigs>
</LightningComponentBundle>
```

## Component Communication
There are two ways to communicate between Independent Components
1) pubsub
2) Lightning Messaging Service

>> NOTE ** Use this approach, if Lightning Messaging Service not serve your purpose. It's an Old technique to communicate with the independent components in LWC

### Pubsub
PubSub module is nothing, just a JavaScript file that contains different methods that are exported so that the other components can make use of it.
It is not provided to you by default, so you have to add it by yourself. It can be simply created by creating a new lightning web component with only JavaScript and meta.xml file.

Let’s take a look over the pubsub.js file.

```js
// Filename:  pubsub.js

/* eslint-disable no-console */
const store = {};
/**
 * subscribers a callback for an event
 * @param {string} eventName - Name of the event to listen for.
 * @param {function} callback - Function to invoke when said event is fired.
 */

const subscribe = (eventName, callback) => {
    if (!store[eventName]) {
        store[eventName] = new Set();
    }
    store[eventName].add(callback);
};

/**
 * unsubscribe a callback for an event
 * @param {string} eventName - Name of the event to unsubscribe from.
 * @param {function} callback - Function to unsubscribe.
 */
const unsubscribe = (eventName, callback) => {
    if (store[eventName]) {
        store[eventName].delete(callback);
    }
};

/**
 * Publish an event to listeners.
 * @param {string} eventName - Name of the event to publish.
 * @param {*} payload - Payload of the event to publish.
 */

const publish = (eventName, payload) => {
    if (store[eventName]) {
        store[eventName].forEach(callback => {
            try {
                callback(payload);
            } catch (error) {
                console.error(error);
            }
        });
    }
};

export default {
    subscribe,
    unsubscribe,
    publish
};
```

// Component PubsubComponentA
```html
<template>
    <lightning-card title="Pubsub demo Component A">
        <div class="slds-p-around_medium">
            <lightning-input type="text" onkeyup={inputHandler} class="slds-m-bottom_medium"></lightning-input>
            <lightning-button variant="brand" onclick={publishHandler} label="publish"></lightning-button>
        </div>
    </lightning-card>
</template>
```

```js
import { LightningElement } from 'lwc';
import pubsub from 'c/pubsub'
export default class PubsubComponentA extends LightningElement {
    message
    inputHandler(event){
        this.message = event.target.value
    }
    publishHandler(){
        pubsub.publish('componentA', this.message)
    }
}
```

// Component PubsubComponentB
```html
<template>
    <lightning-card title="Pubsub demo Component B">
        <div class="slds-p-around_medium">
            Message Recieved - {message}
        </div>
    </lightning-card>
</template>
```

```js
import { LightningElement } from 'lwc';
import pubsub from 'c/pubsub'
export default class PubsubComponentB extends LightningElement {
    message
    connectedCallback(){
        this.callSubscriber()
    }
    callSubscriber(){
        pubsub.subscribe('componentA', (message)=>{
            this.message = message
        })
    }
}
```

### Lightning Messaging Service

Reference Link : https://medium.com/@sendtosachin27/communication-through-lms-in-lwc-748290185c9c

How Component will communicate through Lightning Message Service (LMS) in LWC

##### Define Message Channel Metadata in your org
- Make a folder under force-app/main/default with name "messageChannels".
- Create an xml file "messageChannelName.messageChannel-meta.xml"
- Define lightning message field in .xml file, see code below

```xml
<?xml version="1.0" encoding="UTF-8"?>
<LightningMessageChannel xmlns="http://soap.sforce.com/2006/04/metadata">
    <masterLabel>SampleMessageChannel</masterLabel>
    <isExposed>true</isExposed>
    <description>This is a sample Lightning Message Channel.</description>
    
<!--A list of message payload fields for a given Lightning Message Channel.-->
    <lightningMessageFields>
        <fieldName>recordId</fieldName>
        <description>This is the record Id that changed</description>
    </lightningMessageFields>
    <lightningMessageFields>
        <fieldName>recordData</fieldName>
        <description>The current data representing the record that changed</description>
    </lightningMessageFields>

</LightningMessageChannel>
```

**Import message service**

```js
import msgService from '@salesforce/messageChannel/messageChannelName__c';
```

**import message service features**
```js
import {publish,subscribe,unsubscribe,APPLICATION_SCOPE,MessageContext} from 'lightning/messageService';
```

**Define the Scope of the Message Service**
The Lightning message service lets you define the scope of where subscribing components receive messages in your application.

>> For Lightning web components, the scoping feature is available only when using **@wire adapter**

```js
@wire(MessageContext)
messageContext
```

**Publish Message Channel**</br></br>
To publish message, we have publish() method in Lightning message service’s.</br>
publish() method accept 3 parameter :-</br>
1. Message Context (Type Object)
2. Message Channel (Type Object)
3. Message Payload (The message payload is a JSON object)

#### Example

// Component lmsComponentA

```html
<template>
    <lightning-card title="LWC LMS Component A">
        <div class="slds-m-around_medium">
            <lightning-input type="text" label="Enter message to publish" onkeyup={inputHandler}></lightning-input>
        </div>
        <div class="slds-m-around_medium">
            <lightning-button label="Publish" onclick={publishButtonHandler}></lightning-button>
        </div>
    </lightning-card>
    <c-lms-component-b></c-lms-component-b>
</template>
```
```js
import SAMPLEMC from '@salesforce/messageChannel/SampleMessageChannel__c';
import { MessageContext, publish } from 'lightning/messageService';
import { LightningElement, wire } from 'lwc';

export default class LmsComponentA extends LightningElement {
    
    inputValue;

    @wire(MessageContext)
    context;

    inputHandler(event) {
        this.inputValue = event.target.value;
    }

    publishButtonHandler(){
        const message = {
            recordId : 1234321,
            lmsData: {
                value : this.inputValue
            },
            myMsg : 'Hello'
        }
        console.log('message => ', message);
        //publish(messageContext: Object, messageChannel: Object, message?: Object, publisherOptions?: Object)
        publish(this.context,SAMPLEMC, message);
    }
}
```

// Component lmsComponentB

```html
<template>
    <lightning-card title="LWC LMS Component A">
        <div class="slds-m-around_medium">
            <p>
                Received Message : <strong>{receivedMessage}</strong>
            </p>
        </div>
    </lightning-card>
    <c-lms-component-y></c-lms-component-y>
</template>
```
```js
import SAMPLEMC from '@salesforce/messageChannel/SampleMessageChannel__c';
import { APPLICATION_SCOPE, MessageContext, subscribe } from 'lightning/messageService';
import { LightningElement, wire } from 'lwc';

export default class LmsComponentX extends LightningElement {
   receivedMessage;

    @wire(MessageContext)
    context;

    connectedCallback() {
        this.subscribeMessage();
    }

    subscribeMessage( ){
        subscribe(this.context, SAMPLEMC, (message) => {this.handleMessage(message)}, {scope: APPLICATION_SCOPE})
    } 

    handleMessage(message){
        this.receivedMessage = message.lmsData.value ? message.lmsData.value : 'No Message' 
        console.log(message);
    }
}
```

## Locker Service in Lightning Web Components
Locker Service is a security architecture in Salesforce that enhances the security of Lightning components (both Aura and Lightning Web Components).

Lightning Locker is a layer which sits in between your browser and DOM (document object). In other words, Lightning Locker is a virtual browser that allows only secure request to go through and have access to real DOM. This virtual browser sits in front of your unsafe real browser.

#### How to disable lightning locker?
You can disable lightning locker by changing the api version of lightning component bundle to 39 or below.


#### How to enable lightning locker?
Lightning locker is automatically enabled for component bundles having api version 40 or above.

## Call LWC in Visualforce Page

To load your LWC or Aura Component inside the VF page we will use the $Lightning.use() method.

The **$Lightning.use()** function takes four arguments & they are as follows:

- appName(String): Required* (The name of our lightning dependency app, including namespace. For example, “c:visualforceAuraApplications”)

> Note: We must follow ‘Camel Case’ notation while calling our LWC component inside our Aura Application

- Callback(function): A function to call once the Lightning Component framework and our app have fully loaded. The callback receives no arguments. This callback is usually where you call $Lightning.createComponent() to add our app to the page
- lightningEndPointURL(String): Optional if we are using inside Salesforce. The URL for the Lightning domain on your Salesforce instance. For example, https://MyDomain.lightning.force.com.
- authToken: Optional if we are using inside Salesforce.
  
VF Page Code:

```apex
<apex:page standardStylesheets="true" showHeader="false">
	<apex:includeLightning />    
	<div id="LwcId" />
	<script>
             $Lightning.use("c:visualforceAuraApplications", function() {
	        $Lightning.createComponent("c:callingLwcInVfPages",
	        {
	            note   : 'I am coming from VF Page', // You can pass the value to @api attributes if you have inside JavaScript Class.
	            recordId : '{!$CurrentPage.parameters.id}'
	        },
	        "LwcId", // the Id of div tag where your component will be rendered
	        function(cmp) {
	            console.log('Calling the LWC Component');
	        });
	    });
	</script>
</apex:page>
```

Reference : https://hicglobalsolutions.com/blog/how-to-call-lwc-in-visualforce-pages/

## Call Thirdparty API in LWC
Content security policy (CSP) is used by the Lightning Component framework to restrict content. The main goal is to aid in the prevention of cross-site scripting (XSS) and other code injection attacks.

Let’s add CSP trusted site to Salesforce org in order to make an API call from javascript code without error.

In this example, I’ll use the data-faker API hosted on Heroku: this is the endpoint https://data-faker.herokuapp.com that I’ll use to make a callout from javascript code.

Go to setup > search ‘ CSP ‘ > click on CSP Trusted Sites

![image](https://github.com/therishabh/salesforce-lwc/assets/7955435/49bc81e3-c513-41a6-aeae-6d8c5c610d10)
Create a CSP trusted site by clicking on ‘New Trusted Site,’ as shown in the screenshot below.

![image](https://github.com/therishabh/salesforce-lwc/assets/7955435/9708724e-a421-44b7-b66d-ca502190aa90)

We are now ready to make a callout from javascript code in the lightning web component.

```js
import { LightningElement } from "lwc";

export default class AsyncDemo extends LightningElement {

	connectedCallback() {

		this.callThirdPartyApi(); // call using async await..
        this.callThirdPartySecondApi(); // call using then catch.
	}

	async callThirdPartyApi() {
		// here we are using try and catch to capture error.
		try {
			const response = await fetch('https://jsonplaceholder.typicode.com/todos/1');
			const data = await response.json();
			console.log("ThirdParty API Data", data); // data will print in 
		}
		catch(error){
			console.log('error', error.message);
		}
	}

    callThirdPartySecondApi() {
        fetch('https://jsonplaceholder.typicode.com/todos/1')
        .then(response => response.json())
        .then(json => console.log(json))
    }
}

```

## Check User Permissions for Logged-In User in Lightning Web Component
```js
//to check standard permission

import hasPermission from '@salesforce/userPermission/PermissionName';

//to check custom permission
import hasCustomPermission from '@salesforce/customPermission/Custom_Permission_Api_Name';
```

```js
// userPermissionCheck.js
import { LightningElement } from 'lwc';
import hasRunReports from '@salesforce/userPermission/RunReports';

export default class PermissionCheck extends LightningElement {
    get isRunReport() {
        return hasRunReports;
    }
}
```
```html
<!-- userPermissionCheck.html -->
<template>
    <lightning-card title="User Permisison Check Example">
    <template if:true={isRunReport}>
        <h2>User has Permission to Run Reports.</h2>
    </template>

    <template if:false={isRunReport}>
        <h2>User Does Not have Permission to Run Reports.</h2>
    </template>
</lightning-card>
</template>
```
