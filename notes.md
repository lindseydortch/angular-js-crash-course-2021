# Angular Crash Course 2021 

(angular-overview BRANCH STARTS HERE)
## Intro & Slides 
- Angular is an application design framework and development platform for creating efficient and sophisticated single-page-apps 
  - Angular, like other frontend frameworks, is generally used to create single-page apps that run on the client, but can also be used to create full stack applications by making HTTP requests to a backend server (eg. MEAN stack)
  - Angullar can be run on the server-side with something like Angular Universal
- Why Use Angular? 
  - Create dynamic frontend apps & UIs
  - Full featured framework (router, http, etc)
  - Integrated TypeScript (optional)
  - RxJS - efficient, asynchronous programming 
  - Test-friendly
  - Popular in enterprise business 
- What shoud you know first? 
  - Like with any framework, you should be comfortable with the underlying language first. In this case, that is JavaScript 
    - JavaScript Fundamentals 
    -  Async Programming (promises)
    - Array methods (forEach, map, filter, etc)
    - Fetch API / HTTP Requests 
    - NPM (Node Package Manager)
- Angular Components 
  - Components are pieces of the UI including the template (html), logic and styling
  - Components are reusable and can be embedded into the template as an XML-like tag
- Angular Services 
  - Angular distinguishes components from services to increase modularity and reusablity 
  - By seprating a component's view-related functionality from other kinds of processing, you can make your component classes lean and efficient 
  - A compoennt can delegate certain tasks to services, such as fetching data from the server, validating user input, or logging directly to the console 
- Angular CLI 
  - Standard tooling for Angular development 
    - Command line interface for creating angular apps 
    - Dev server and easy production build 
    - Commands to generate components, services, etc. 
  - CLI Commands
    - npm i -g @angular/cli
    - ng new my-app

## Angular CLI & Setup 
- You use ng serve to run the dev server 

## Files & Folders 
- tscongif, for if you need to change any TypeScript settings 
- angular.json - change any outputs and CDN's 
- src/app - main folder, where all of your components and services go 
  - index.html - uses the app-root 
  - main.ts - the gateway to your Angular app 
  - app.module.ts - imports are where any modules go, and then providers  

## Component Structure 
- When you create a component, you're generally going to have 4 files 
  - html, component.ts, spec.ts, css

## Properties & Interpolation 
- We use {{}} for interpolation 

## Global Styles 
- Put your global styles in the styles.css
- Any app specific styles will go in the component.css

## Header Component 
- To create a new component run `` in the terminal
- ngOnInit - lifecycle method 
  - If you want it to run if the component loads 

## Button Component 
- Created a button component using the ng generate component method 

## Component Input Data 
- To bring in input, you import it from @angular/core at the top of your component
- When bringing in an @Input add a ! after your input 
- To pass down a style, you're going to use [ngStyle]="{'property': input}"

## Creating An Event & Event Emitter Output 
- To add an event you use (eventName)="onClick()"
  - You don't want to put the functionality in our button, we're going to bring in an event emitter
- To add an event emitter, you are going to use @Output

## Mock Tasks & Task Interface
- JSONServer, a fake API 
- Interfaces are like models 
- If it's an array you want to add brackets 

## Tasks Component 
- tasks: Task[] = TASKS; added to the top of your component before the constructor and lifecycle method 

## Looping With ngFor 
- To loop through a task in your HTML you use *ngFor 

## Task Item Component 
- Added this component to our Tasks component HTML and was able to pass down the tasks 

## Angular Font Awesome Setup 
- Use this repo to add in here: `https://github.com/FortAwesome/angular-fontawesome`
- Angular adds and imports each module everytime you create a component 

## Create A Task Service 
- To create a service you run `ng generate service service-name`
- Services are just a class with an Injectable 
- In order to use a service you have to use it as a Provider in the constructor 
- You call the service in the ngOnInit() 
  - void just means this particular function doesn't return anything

## Creating And Subscribe To Observable 
- You want to return Observables because you want to return asynchronous data 
- You subscribe to an Observable so you can constantly watch it 
  - Think of subscribing as a promise 
  - You want to subscribe to your function to keep watching it 

(angular-overview BRANCH ENDS HERE)
(server-setup BRANCH STARTS HERE)
## JSON-Server Setup
- We will be using the HttpClient to return data
- The HttpClient returns an Observable automatically 
- You won't have to use of 
- For the backend we are using JSON Server 
  - Not made for production, can only be used locally 

## Angular HTTP Client 
- HttpClient is included with Angular 
- In order to use the HttpClient, you have to add it as a module 

## Fetching Tasks 
- this.http<Task[]>(this.apiUrl)

## Deleting Tasks 
- You can add this in the task component 
- In order to delete the task you need to get the ID
- Think of the subscribe as a .then()  

## Toggle Reminder 
- Just like we have [ngStyle], we also have access to [ngClass]

## Add Task Component 
- When working with forms you want to add define them above your constructor 

## Forms Module & ngModel 
- ngModel is part of the formsModule and is not setup by default 
- brackets are for input
- () are used for events and output
- For ngModel we use both [()] - it's a two-way binding 

## Submit & Create Task 
- There's an ngSubmit that we can use on the form 
- $event in your function lets you call a new task 

## Toggle Button & UI Service 
- Instead of passing things around (prop drilling) we're going to create a service and set up a subject 
- You bring in Observable and Subject 
- We can use an *ngIf to tell your HTML whether or not you want it to show 

(server-setup BRANCH ENDS HERE)
(angular-router BRANCH STARTS HERE)
## Angular Router
- You can set this up when you set up the app 
- You use the <router-outlet> to give your component a path 
- href refreshes the page, you use routerLink instead

## Limit Component To Route 
- We don't want to show the add task button on the about page 
- You can use router to compare and show the button only on the / route 