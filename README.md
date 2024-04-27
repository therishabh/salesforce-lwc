# Salesforce LWC

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



