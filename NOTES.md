# Angular

### Intro to Modules

- compilation context for components
- collect related code into functional sets
- a set of NgModules define an angular app

Note: An app always has at least a root module (AppModule) that enables bootstrapping, and typically has many more
feature modules

```js
// app.module.ts
import { BrowserModule } from "@angular/platform-browser";
import { NgModule } from "@angular/core";

import { AppComponent } from "./app.component";

@NgModule({
  declarations: [AppComponent],
  imports: [BrowserModule],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule {}
```

```js
// app.component.ts
import { Component } from "@angular/core";

@Component({
  selector: "app-root",
  templateUrl: "./app.component.html",
  styleUrls: ["./app.component.scss"]
})
export class AppComponent {
  title = "learn-angular";
}
```

```html
<!--index.html-->
<body>
  <app-root></app-root>
</body>
```

An NgModule is a class marked by the @NgModule decorator. 
@NgModule takes a metadata object that describes how to compile a component's template and how to create an injector at runtime. 
It identifies the module's own components, directives, and pipes, making some of them public, through the exports property, so that external components can use them. 
@NgModule can also add service providers to the application dependency injectors.

Angular libraries are NgModules, such as FormsModule, HttpClientModule, and RouterModule. 
Many third-party libraries are available as NgModules such as Material Design, Ionic, and AngularFire2.

### Intro to Components
