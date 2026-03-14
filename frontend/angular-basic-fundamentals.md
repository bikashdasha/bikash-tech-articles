
# ⚡ Angular Fundamentals – Complete Beginner Guide

## 🚀 Introduction

**Angular** is one of the most popular frameworks used to build modern web applications. It is developed and maintained by **Google** and is widely used for creating **dynamic, scalable, and enterprise-level frontend applications**.

Angular allows developers to build **Single Page Applications (SPA)** where the page loads once and dynamically updates content without refreshing the entire page.

This guide explains the **core fundamentals of Angular** that every developer should understand.

This article is helpful for:

* 👨‍🎓 Beginners learning frontend development
* 👨‍💻 Developers transitioning to Angular
* 🧑‍🔬 Engineers preparing for Angular interviews

---

# 📌 What is Angular?

Angular is a **TypeScript-based frontend framework** used to build interactive web applications.

Key features include:

* Component-based architecture
* Two-way data binding
* Dependency injection
* Powerful CLI tools
* Modular application structure

Angular helps developers organize applications into **reusable components and modules**.

---

# ⚙️ Installing Angular

Before starting Angular development, install the following:

### 1️⃣ Install Node.js

Angular requires Node.js to run.

Check installation:

```bash id="a0011"
node -v
npm -v
```

---

### 2️⃣ Install Angular CLI

Angular CLI helps create and manage Angular projects.

```bash id="a0012"
npm install -g @angular/cli
```

Check installation:

```bash id="a0013"
ng version
```

---

### 3️⃣ Create a New Angular Project

```bash id="a0014"
ng new my-angular-app
```

Run the project:

```bash id="a0015"
cd my-angular-app
ng serve
```

Open in browser:

```id="a0016"
http://localhost:4200
```

---

# 🧠 Angular Project Structure

A typical Angular project contains the following folders.

```id="a0017"
src/
 ├── app/
 │   ├── app.component.ts
 │   ├── app.component.html
 │   ├── app.component.css
 │   └── app.module.ts
 ├── assets/
 ├── environments/
 └── index.html
```

Important files:

| File               | Purpose                 |
| ------------------ | ----------------------- |
| app.module.ts      | Main application module |
| app.component.ts   | Root component          |
| app.component.html | UI template             |
| app.component.css  | Styling                 |

---

# 🧩 Angular Components

Components are the **building blocks of Angular applications**.

A component controls a part of the UI.

Example component:

```typescript id="a0018"
import { Component } from '@angular/core';

@Component({
  selector: 'app-hello',
  template: `<h2>Hello Angular!</h2>`
})
export class HelloComponent {}
```

Component parts:

| Property  | Purpose       |
| --------- | ------------- |
| selector  | HTML tag name |
| template  | UI content    |
| styleUrls | CSS styles    |

Usage:

```html id="a0019"
<app-hello></app-hello>
```

---

# 🔗 Angular Modules

Modules help organize Angular applications.

The main module is **AppModule**.

Example:

```typescript id="a0020"
import { NgModule } from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';

@NgModule({
  declarations: [],
  imports: [BrowserModule],
  providers: [],
  bootstrap: []
})
export class AppModule { }
```

Modules allow grouping components, services, and pipes.

---

# 🔄 Data Binding in Angular

Angular supports powerful **data binding techniques**.

---

## 1️⃣ Interpolation

Displays data from the component to the template.

```html id="a0021"
<h2>{{ title }}</h2>
```

Component:

```typescript id="a0022"
title = "Angular Learning Guide";
```

---

## 2️⃣ Property Binding

Used to bind values to HTML properties.

```html id="a0023"
<img [src]="imageUrl">
```

---

## 3️⃣ Event Binding

Handles user events like clicks.

```html id="a0024"
<button (click)="showMessage()">Click Me</button>
```

Component:

```typescript id="a0025"
showMessage(){
  alert("Hello from Angular!");
}
```

---

## 4️⃣ Two-Way Data Binding

Allows data to flow **both ways** between UI and component.

```html id="a0026"
<input [(ngModel)]="username">
<p>{{ username }}</p>
```

---

# 📦 Angular Services

Services are used to **share data and logic across components**.

Example service:

```typescript id="a0027"
import { Injectable } from '@angular/core';

@Injectable({
  providedIn: 'root'
})
export class UserService {

  getUsers(){
    return ["Bikash","John","David"];
  }

}
```

Services help keep components **clean and maintainable**.

---

# 🌐 HTTP Requests in Angular

Angular provides **HttpClient** for calling APIs.

Example:

```typescript id="a0028"
import { HttpClient } from '@angular/common/http';

constructor(private http: HttpClient){}

getUsers(){
  return this.http.get('https://api.example.com/users');
}
```

This allows Angular applications to communicate with backend services.

---

# 📊 Angular Routing

Routing allows navigation between pages.

Example routes:

```typescript id="a0029"
const routes = [
  { path: 'home', component: HomeComponent },
  { path: 'about', component: AboutComponent }
];
```

HTML navigation:

```html id="a0030"
<a routerLink="/home">Home</a>
<a routerLink="/about">About</a>
```

---

# 🧪 Angular CLI Useful Commands

| Command                    | Purpose          |
| -------------------------- | ---------------- |
| ng new app-name            | Create project   |
| ng serve                   | Run application  |
| ng generate component name | Create component |
| ng generate service name   | Create service   |

Example:

```bash id="a0031"
ng generate component user
```

---

# 📚 Important Angular Concepts

Developers should understand these concepts clearly:

* Components
* Modules
* Data Binding
* Directives
* Services
* Dependency Injection
* Routing
* HTTP Client

These form the **foundation of Angular development**.

---

# 📈 Advanced Topics to Learn Next

After mastering the basics, explore:

* Angular Forms (Reactive Forms)
* State Management
* Lazy Loading
* Angular Material
* Performance Optimization

---

# 🎯 Conclusion

Angular is a powerful framework for building scalable and maintainable web applications.

By understanding the **core fundamentals**, developers can create robust frontend applications.

Learning Angular concepts such as:

* Components
* Modules
* Data Binding
* Services
* Routing

will help you build **modern and professional web applications**.

Consistent practice and building projects will strengthen your Angular development skills.

---

⭐ If you found this guide helpful, consider starring the repository and sharing it with other developers.
