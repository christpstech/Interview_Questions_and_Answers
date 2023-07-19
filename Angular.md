### **Angular Interview Questions and Answers**

#

1.  **What are Single Page Applications (SPA)?**

    > - Single page applications are **_web based applications that only need to be loaded once_**.

2.  **What is bootstrapped module**

    > Bootstrapping is the process of **_initializing or loading_** our Angular application.

3.  **What is data binding in angular?**

    > Data binding **_allows communication between component and DOM_** (Document object model).

    ### _There are 4 types of data binding_

    1.  **String interpolation**
        > - String Interpolation is a **_one-way databinding technique._**
        > - Data from a **_TypeScript code to HTML template_** (view).
        #### **Syntax:**
              <li>Name: {{ user.name }}</li>
    2.  **Property Binding**
        > - Property Binding is also a **one-way data binding technique**.
        > - In property binding, we **_bind a property of a DOM element to a field_**
        #### **Syntax:**
                 <input type="email" [value]="user.email">
    3.  **Event Binding**
        > - event binding is **_used to handle the events raised from the DOM_** like button click, mouse move etc.
        #### **Syntax:**
                 <button (click)="cookBacon()"></button>
    4.  **Two-way Data Binding**
        > In two way data binding, **_property binding and event binding are combined together_** (component to veiw and view to component).
        #### **Syntax:**
               [(ngModel)] = "[property of your component]"

4.  **What are directives in Angular?**

    > Directives are classes that **_add additional behavior to elements_** in your Angular applications.
    > _There are 3 types of directives_

    1. **Component Directives**
       > - They are the **directive with a template**

    #### **Example**

            import {Directive, ElementRef, OnInit } from '@angular/core';

            @Directive({
            selector:'[appBasicHighlight]'
            })
            export class basicHighlightDirective{
               constructor(private elementRef :ElementRef){
               }

               ngOnInit(){
                  this.elementRef.nativeElement.style.background = "blue";
               }

            }

    2.  **Attribute Directive**
        > **_Change the appearance or behavior_** of an element, component, or another directive.
        >
        > - Examples of attributes directives are _ngStyle, ngClass, ngModel_
        #### **Example**
                 <div [ngStyle]="{'color': 'blue'}">
                    some text
                 </div>
    3.  **Structural Directives**

        > Structural directives can change the DOM layout by **_adding and removing DOM elements_**.
        >
        > - **\*ngIf** — **adds or removes** element from DOM.
        > - **\*ngFor** — **renders list of elements on every iteration**.
        > - _All structural Directives are preceded by Asterix_ (\*) symbol.

        #### **Example**

                <tr *ngFor="let customer of customers;">
                   <td>{{customer.name}}</td>
                </tr>

5.  **What are the building blocks in angular?**

    > The main building blocks for Angular are **_modules, components, templates, metadata, data binding, directives, services, and dependency injection_**.

6.  **Difference between sessionStorage and localStorage**
