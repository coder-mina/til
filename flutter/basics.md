# Flutter Basics

* How to create a new project
  * $ flutter create [project_name] => create new Flutter project

* How to run emulator

  * editor: VS Code, android studio - AVD Manager - open device.
  * (1) $ flutter run (from the VS Code terminal)
  * (2) debug -> run ->  (from VS Code)

  * Hot reload: r  OR thunder icon.





* (1) flutter run 

  

## files and folders

* Lib: write dart files.
* pubspec.yaml : configure dependencies, fonts, images
* sometimes, modify android, ios folder (if necessary)
* the rest: auto-generated OR passive 



* widget = UI building blocks 
* flutter app = tree of widgets
* 
* can use Dart for web programming
* dart is typed language. (everything is typed)
* main(): entry point of application. (when your app launches this func is called)
* camelCase
* **var** keyword = variable (Because of that built-in type inference, it's considered a **good practice** to NOT explicitly define the type but instead use var when defining variables. )



* MaterialApp class: named arguments.

```dart
class Person {
  String name;
  int age;
  
  // Person({String inputName, int age = 30});
  Person({this.name, this.age = 30});
}

void main() {
  var p1 = Person(name: 'Max', age: 30);
  print(p1.name);
}
```



* runApp() => calls build() of MyApp which inherited StatelessWidget



* flutter calls build method of widgets to draw to the screen : responsible for returning the widget.
* flutter controls all UI, all pixels in your screen.
* Scaffold widget = create basic page design.
* add comma after ) always (visually pretty formatting): shift + alt + F => auto formatting 

build UI by code.



We have different types of widgets in flutter.

- visible: output & input
- invisible: layout & control -> struturing our app.



* list: ex) var questions = ['hello', 'what'];

* stateless  widget 

* setState() = trigger that informs Flutter that it needs to re-run build() of the widget.

* state 버뀌면 widget 을 re-render 해야 한다고 말해줘야. (you can't re-build the widget for every user action or else your app performance will be terrible)

* StatelessWidget can't re-run build() when its properties change.

  (you CAN add and also change properties in a StatelessWidget, there is no way of telling Flutter that it should re-run build() upon such changes.)





## IDE

* control + space : auto completion options
* control + / : comment blocks