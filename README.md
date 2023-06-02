# AngularLifecycleHooks
 Component Lifecyles of an Angular application demo
[Angular page for full documentation:](https://angular.io/guide/lifecycle-hooks)
 # Topics
## Peek-A-Boo
Example which shows the call order of lifecyle hooks by creating
and destroying a child component. One can see the corresponding order by creating and destroying the child component:
 1. Constructor call
 2. On Changes call
 3. OnInit call
 4. DoCheck call
 5. AfterContentInit call
 6. AfterContentChecked call
 7. AfterViewInit call
 8. AfterViewChecked call
 9. DoCheck call
10. AfterContentChecked call
11. AfterViewChecked call
12. OnDestroy call

## SpyDirective
Demonstrates how hooks can be integrated in simple directives.
The example implement a directive in a <p> tag so that one can see the **OnInit** and **OnDestroy** calls, if the <p> tag is created or
destroyed.

## OnChanges
Shows how one can **track changes in input attributes** with the **OnChanges** hook. One should always consider that when the input parameter is an object, than the object change is tracked, but not the change of its properties. Current and previous values can
be queried.

## DoCheck
Shows how to implement the **DoCheck** hook with which one can create **custom checks**. The example shows to track properties of an object input attribute of a component. One should consider that this hook can be expensive when building real world applications.

## AfterView
This shows how to implement the **AfterViewInit** and **ngAfterViewChecked** which must be implemented if you want to **invert the dataflow from parent to child to child to parent component**. Thus the **parent can track changes in child components**.
This hooks are called after Angular creates its corresponding child views of the parent component.

## AfterContent
The main purpose of the following hooks is to provide *content projection*, i.o.w. to import HTML content from outside the component and insert it inside. The example is similarly the AfterView example. These hooks are AfterContentInit and AfterContentChecked. The `<ng-content>` directive is used as placeholder for the provided content. **Similarly the parent component can track changes of child components.**

## Counter Spy
A Counter uses the ngOnChanges() method to log a change every time the parent component increments its input counter property. The child component
uses the ***appSpy*** directive to write messages in the logger instance during the **OnInit** and **OnDestroy** hooks. The parent component represents a view for the logs.

### Important to understand
The LoggerService.tick_then() statement postpones the log update for one turn of the browser's JavaScript cycle, which triggers a new change-detection cycle.


# Running the application (locally)
## Starting the Angular application
`ng serve`