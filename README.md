## Table of Contents

| No. | Topics |
| --- | --------- |
|1 | [Set Up](#set-up)|
|2 | [Running Script for .ts file](#running-script-for-.ts-file)|
|3 | [Why TypeScript](#why-typeScript)|
|4 | [Types in TypeScript](#types-in-typeScript)|
|4.1 | [2 categories of TypeScript Types](#types-in-typeScript)|
|4.2 | [Type Annotations](#types-in-typeScript)|
|4.3 | [Type Inference](#types-in-typeScript)|
|4.4 | [number](#types-in-typeScript)|
|4.4 | [string](#types-in-typeScript)|
|4.5 | [boolean](#types-in-typeScript)|
|4.6 | [object](#types-in-typeScript)|
|4.7 | [array](#types-in-typeScript)|
|4.8 | [enum](#types-in-typeScript)|
|4.9 | [any](#types-in-typeScript)|
|4.10 | [void](#types-in-typeScript)|
|4.11 | [never](#types-in-typeScript)|
|4.12 | [Union](#types-in-typeScript)|
|4.13 | [Type Aliases](#types-in-typeScript)|
|4.14 | [String Literals](#types-in-typeScript)|
|5 | [TypeScript Functions](#typeScript-functions)|
|5.1 | [Optional Parameters](#typeScript-functions)|
|5.2 | [Default Parameters](#typeScript-functions)|
|6 | [TypeScript Classes](#typeScript-classes)|
|6.1 | [Class](#typeScript-classes)|
|6.2 | [Readonly](#typeScript-classes)|
|6.3 | [Getters and Setters](#typeScript-classes)|
|6.4 | [Inheritance](#typeScript-classes)|Abstract Classes
|6.5 | [Static Methods and Properties](#typeScript-classes)|
|6.6 | [Abstract Classes](#typeScript-classes)|
|7 | [Interface](#interface)|
|7.1 | [Extending Interfaces](#interface)|
|8 | [Advanced Types](#advanced-types)|
|8.1 | [Intersection Types](#advanced-types)|
|8.2 | [Type Guards](#advanced-types)|
|8.3 | [Type Casting](#advanced-types)|
|8.4 | [Type Assertions](#advanced-types)|
|8 | [Generics](#generics)|
|8.1 | [TypeScript Generics](#generics)|
|8.2 | [Generic Constraints](#generics)|
|8.3 | [Generic Classes](#generics)|
|8.4 | [Interface Generics](#generics)|
## Set Up
* Node Environment
* TypeScript Compiler such as typescript package: To compile TS code to JS code
* Code Editor
*    **[⬆ Back to Top](#table-of-contents)**
## Running Script for .ts file
* `tsc app.ts` ; then, `node app.js` for  `typescript` package
* `ts-node app.ts` for `ts-node` package
*   **[⬆ Back to Top](#table-of-contents)**
## Why TypeScript
* JavaScript is dynamically typed. It offers flexibility but also creates many problems.
* TypeScript adds an optional type system to JavaScript to solve these problems.
*    **[⬆ Back to Top](#table-of-contents)**
## Types in TypeScript
* In general, every value in TypeScript has a type. A type is a label that describes the properties and methods that a value has. TypeScript compiler uses types to analyze your code for hunting bugs and errors.
*   **[⬆ Back to Top](#table-of-contents)**
### 2 categories of TypeScript Types
* Primitive Types: `string`, `number`, `boolean`, `null`, `undefined`, `symbol`
* Object Types: `function`, `array`, `classes`
*    **[⬆ Back to Top](#table-of-contents)**
### Type Annotations
* It is used to explicitly specify types for identifiers such variables, functions, objects, etc.
* Syntax
```
    let counter: number = 1;
```
* Array: `let names: string[] = ['John', 'Jane', 'Peter', 'David', 'Mary'];`

* Object: 
```
    let person: {
    name: string;
    age: number
    };
```
* Function Argument and Return Type: `let greeting : (name: string) => string;`
* Type Annotation is used when:
1. When you declare a variable and assign it a value later.
2. When you want a variable that can’t be inferred.
3. When a function returns the any type and you need to clarify the value.
*    **[⬆ Back to Top](#table-of-contents)**
### Type Inference
* Type Inference is that TypeScript uses the best common type algorithm to analyze each candidate type and select the type that is compatible with all other candidates. That is, TypeScript guesses the type based on context.
* Type Inference is used when: initialize variables, set parameter default values, and determine function return types.
*    **[⬆ Back to Top](#table-of-contents)**
### number
* `number`: floating-point values, including integers, decimal numbers, binary, octal numbers, hex, 
* `bigint`: big integers, which are larger than 2^53 – 1
*    **[⬆ Back to Top](#table-of-contents)**
### string
* TypeScript uses double quotes ("), single quotes ('), and backtick (`) to surround string literals.
*    **[⬆ Back to Top](#table-of-contents)**
### boolean
* `boolean` type allows two values: true and false
*    **[⬆ Back to Top](#table-of-contents)**
### object
* The TypeScript `object` type represents any value that is not a primitive value.
```
    let employee: {
        firstName: string;
        lastName: string;
        age: number;
        jobTitle: string;
    };
```
* The `Object` type, however, describes functionality that available on all objects. The `Object` type has the `toString()` and `valueOf()` methods that can be accessible by any object.
* The empty type `{}` refers to an object that has no property on its own.
*    **[⬆ Back to Top](#table-of-contents)**
### array
* As an array can store a mixed type of values, it is better for TypeScript infer type for the array
* TypeScript arrays can access the properties and methods of a JavaScript such as `length`, `push`,`forEach()`, `map()`, `reduce()`, and `filter()`
*    **[⬆ Back to Top](#table-of-contents)**
### tuple
* Similar to `array`, but:
1. The number of elements in the tuple is fixed.
2. The types of elements are known, and need not be the same.
* `?` represents optional elements
```
    let bgColor, headerColor: [number, number, number, number?];
```
*   **[⬆ Back to Top](#table-of-contents)**
### enum
```
    enum ApprovalStatus {
        draft,
        submitted,
        approved,
        rejected
    };
    let isApproved: boolean = status === ApprovalStatus.approved;
```
* A TypeScript enum is a group of constant values.
* Under the hood, an enum a JavaScript object with named properties declared in the enum definition.
*   **[⬆ Back to Top](#table-of-contents)**
### any
* The TypeScript any type allows you to store a value of any type. It instructs the compiler to skip type checking.
* Use the any type to store a value that you don’t actually know its type at the compile-time or when you migrate a JavaScript project over to a TypeScript project.
*    **[⬆ Back to Top](#table-of-contents)**
### void
* The `void` type is used as the return type of functions that do not return any value.
*    **[⬆ Back to Top](#table-of-contents)**
### never
* The `never` type contains no value.
* The `never` type represents the return type of a function that always throws an error or a function that contains an indefinite loop.
```
    function raiseError(message: string): never {
        throw new Error(message);
    }
```
*   **[⬆ Back to Top](#table-of-contents)**
### union
* A TypeScript union type allows you to store a value of one or serveral types in a variable.
```
    let result: number | string;
    result = 10; // OK
    result = 'Hi'; // also OK
    result = false; // a boolean value, not OK
```
*    **[⬆ Back to Top](#table-of-contents)**
### Type Aliases
* Use type aliases to define new names for existing types.
```
    type alphanumeric = string | number;
    let input: alphanumeric;
    input = 100; // valid
    input = 'Hi'; // valid
    input = false; // Compiler error
```
*    **[⬆ Back to Top](#table-of-contents)**
### String Literals
* A TypeScript string literal type defines a type that accepts specified string literal.
* Use the string literal types with union types and type aliases to define types that accept a finite set of string literals.
```
    type MouseEvent: 'click' | 'dblclick' | 'mouseup' | 'mousedown';
    let mouseEvent: MouseEvent;
    mouseEvent = 'click'; // valid
    mouseEvent = 'dblclick'; // valid
```
 *   **[⬆ Back to Top](#table-of-contents)**
## TypeScript Functions
### **Syntax**: 
1. 

```
    function name(parameter: type, parameter:type,...): returnType {
    // do something
    }
```
2. 
```
    (parameter: type, parameter:type,...) => type
```
3. 
```
    add = function (x: string, y: string): number {
        return x.concat(y).length;
    };
```
*   **[⬆ Back to Top](#table-of-contents)**
### Optional Parameters
* Use the parameter `?:` type syntax to make a parameter optional.
* Use the expression `typeof(parameter) !== 'undefined'` to check if the parameter has ben initialized.
```
    function multiply(a: number, b?: number, c: number): number {

        if (typeof c !== 'undefined') {
            return a * b * c;
        }
        return a * b;
    }
```
*    **[⬆ Back to Top](#table-of-contents)**
### Default Parameters
* Use default parameter syntax `parameter:=defaultValue` if you want to set the default initialized value for the parameter.
* Default parameters are optional.
* To use the default initialized value of a parameter, you omit the argument when calling the function or pass the `undefined` into the function.
```
    function applyDiscount(price: number, discount: number = 0.05): number {
        return price * (1 - discount);
    }
```

*   **[⬆ Back to Top](#table-of-contents)**
### Rest Parameters
* A rest parameter allows you a function to accept zero or more arguments of the specified type.
* Note: 
    1. A function has only one rest parameter.
    2. The rest parameter appears last in the parameter list.
    3. The type of the rest parameter is an array type.
```
    function getTotal(...numbers: number[]): number {
        let total = 0;
        numbers.forEach((num) => total += num);
        return total;
    }
```

*    **[⬆ Back to Top](#table-of-contents)**
### Function Overloading
* It is used to relate functions with the same signatures
```
    function add(a: number, b: number): number;
    function add(a: string, b: string): string;
    function add(a: any, b: any): any {
    return a + b;
    }
```
* There is method overloading in object
```
    class Counter {
        private current: number = 0;
        count(): number;
        count(target: number): number[];
        count(target?: number): number | number[] {
            if (target) {
                let values = [];
                for (let start = this.current; start <= target; start++) {
                    values.push(start);
                }
                this.current = target;
                return values;
            }
            return ++this.current;
        }
    }
```
*    **[⬆ Back to Top](#table-of-contents)**
## TypeScript Classes
### Class
```
    class Person {
        ssn: string;
        firstName: string;
        lastName: string;

        constructor(ssn: string, firstName: string, lastName: string) {
            this.ssn = ssn;
            this.firstName = firstName;
            this.lastName = lastName;
        }

        getFullName(): string {
            return `${this.firstName} ${this.lastName}`;
        }
    }
```
* Also, class methods can be created by prototype inheritance
```
    Person.prototype.getFullName = function () {
        return `${this.firstName} ${this.lastName}`;
    }
```
*    **[⬆ Back to Top](#table-of-contents)**
### Access Modifiers
* TypeScript provides three access modifiers to class properties and methods: ``private``, ``protected``, and ``public``.
* The ``private`` modifier allows access within the same class.
* The ``protected`` modifier allows access within the same class and subclasses.
* The ``public`` modifier allows access from any location.

```
    class Person {
        constructor(protected ssn: string, private firstName: string, private lastName: string) {
            this.ssn = ssn;
            this.firstName = firstName;
            this.lastName = lastName;
        }

        getFullName(): string {
            return `${this.firstName} ${this.lastName}`;
        }
    }
```
*    **[⬆ Back to Top](#table-of-contents)**
### Readonly
* Use the  ``access`` modifier to mark a class property as immutable.
* A ``readonly`` property must be initialized as a part of the declaration or in the constructor of the same class.
```
    class Person {
        readonly birthDate: Date;

        constructor(birthDate: Date) {
            this.birthDate = birthDate;
        }
    }
```
*    **[⬆ Back to Top](#table-of-contents)**
### Getters and Setters
* Use TypeScript getters/setters to control the access properties of a class.
* The getter/setters are also known as accessors/mutators.
```
    class Person {
        // ... other code 
        public get fullName() {
            return `${this.firstName} ${this.lastName}`;
        }

        public set fullName(name: string) {
            let parts = name.split(' ');
            if (parts.length != 2) {
                throw new Error('Invalid name format: first last');
            }
            this.firstName = parts[0];
            this.lastName = parts[1];
        }
    }
```
*    **[⬆ Back to Top](#table-of-contents)**
### Inheritance
* Use the ``extends`` keyword to allow a class to inherit from another class.
* Use ``super()`` in the constructor of the child class to call the constructor of the parent class. Also, use the ``super.methodInParentClass()`` syntax to invoke the ``methodInParentClass()`` in the method of the child class.
```
    class Employee extends Person {
        constructor(firstName: string, lastName: string, private jobTitle: string) {
            super(firstName, lastName);
        }
        describe(): string {
            return super.describe() + `I'm a ${this.jobTitle}.`;
        }
    }
```
*    **[⬆ Back to Top](#table-of-contents)**
### Static Methods and Properties
* Static properties and methods are shared by all instances of a class.
* Use the ``static`` keyword before a property or a method to make it static.
```
class Employee {
    private static headcount: number = 0;

    constructor( //codes go here){
        Employee.headcount++;
    }

    public static getHeadcount() {
        return Employee.headcount;
    }
}
```
*    **[⬆ Back to Top](#table-of-contents)**
### Abstract Classes
* Abstract classes cannot be instantiated.
* An Abstract class has at least one abstract method.
* To use an abstract class, you need to inherit it and provide the implementation for the abstract methods.
```
    abstract class Employee {
        constructor(private firstName: string, private lastName: string) {
        }
        abstract getSalary(): number
        get fullName(): string {
            return `${this.firstName} ${this.lastName}`;
        }
        compensationStatement(): string {
            return `${this.fullName} makes ${this.getSalary()} a month.`;
        }
    }
```
```
    class FullTimeEmployee extends Employee {
        constructor(firstName: string, lastName: string, private salary: number) {
            super(firstName, lastName);
        }
        getSalary(): number {
            return this.salary;
        }
    }
```
*    **[⬆ Back to Top](#table-of-contents)**
## Interface
* TypeScript interfaces define contracts in your code and provide explicit names for type checking.
* Interfaces may have optional properties or readonly properties.
* Interfaces can be used as function types.
* Interfaces are **typically used as class types that make a contract between unrelated classes**.
```
    interface Json {
        toJSON(): string
    }

    class Person implements Json {
        constructor(private firstName: string,
            private lastName: string) {
        }
        toJson(): string {
            return JSON.stringify(this);
        }
    }    
```
*    **[⬆ Back to Top](#table-of-contents)**
### Extending Interfaces
* An interface can extend one or multiple existing interfaces.
* An interface also can extend a class. **If the class contains private or protected members, the interface can only be implemented by the class or subclasses of that class**.
```
    class Control {
        private state: boolean;
    }

    interface StatefulControl extends Control {
        enable(): void
    }

    class Button extends Control implements StatefulControl {
        enable() { }
    }

    // Error: cannot implement
    class Chart implements StatefulControl {
        enable() { }

    }
```
*    **[⬆ Back to Top](#table-of-contents)**
## Advanced Types
### Intersection Types
* An intersection type combines two or more types to create a new type that **has all properties of the existing types**.
* The type order is not important when you combine types.
```
    interface BusinessPartner {
        name: string;
        credit: number;
    }

    interface Identity {
        id: number;
        name: string;
    }

    interface Contact {
        email: string;
        phone: string;
    }

    type Employee = Identity & Contact;
    type Customer = BusinessPartner & Contact;
```
*    **[⬆ Back to Top](#table-of-contents)**
### Type Guards
* Type guards narrow down the type of a variable within a conditional block.
* Use the ``typeof`` and ``instanceof`` operators to implement type guards in the conditional blocks
* User-defined Type Guards: A user-defined type guard function is a function that simply returns ``arg is aType``
```
    function isCustomer(partner: any): partner is Customer {
        return partner instanceof Customer;
    }
```
*    **[⬆ Back to Top](#table-of-contents)**
### Type Casting
* Type casting allows you to convert a variable from one type to another.
* Use the ``as`` keyword or ``<>`` operator for type castings.`
```
    let a: typeA;
    let b = <typeB>a;
```

```
    let input = document.querySelector('input[type="text"]') as HTMLInputElement;
```
*    **[⬆ Back to Top](#table-of-contents)**
### Type Assertions
* Type assertions instruct the compiler to treat a value as a specified type.
* Type assertions do not carry any type conversion.
* Type assertions use the ``as`` keyword or an angle bracket ``<>`` syntax.
*    **[⬆ Back to Top](#table-of-contents)**
## Generics
### TypeScript Generics
* Use TypeScript generics to develop reusable, generalized, and type-safe functions, interfaces, and classes.
```
    function merge<U, V>(obj1: U, obj2: V) {
        return {
            ...obj1,
            ...obj2
        };
    }
```
* Benefits:
1. Leverage type checks at the compile time.
2. Eliminate type castings.
3. Allow you to implement generic algorithms.
*    **[⬆ Back to Top](#table-of-contents)**
### Generic Constraints
* Use ``extends`` keyword to constrain the type parameter to a specific type.
```
    function merge<U extends object, V extends object>(obj1: U, obj2: V) {
        return {
            ...obj1,
            ...obj2
        };
    }
```
* Use ``extends keyof`` to constrain a type that is the property of another object.
```
    function prop<T, K extends keyof T>(obj: T, key: K) {
        return obj[key];
    }
```
*    **[⬆ Back to Top](#table-of-contents)**
### Generic Classes
```
    class Stack<T> {
        private elements: T[] = [];

        constructor(private size: number) {
        }
        isEmpty(): boolean {
            return this.elements.length === 0;
        }
        isFull(): boolean {
            return this.elements.length === this.size;
        }
        push(element: T): void {
            if (this.elements.length === this.size) {
                throw new Error('The stack is overflow!');
            }
            this.elements.push(element);

        }
        pop(): T {
            if (this.elements.length == 0) {
                throw new Error('The stack is empty!');
            }
            return this.elements.pop();
        }
    }

    let numbers = new Stack<number>(5);
```
*    **[⬆ Back to Top](#table-of-contents)**
### Interface Generics
```
    interface Collection<T> {
        add(o: T): void;
        remove(o: T): void;
    }

    class List<T> implements Collection<T>{
        private items: T[] = [];

        add(o: T): void {
            this.items.push(o);
        }
        remove(o: T): void {
            let index = this.items.indexOf(o);
            if (index > -1) {
                this.items.splice(index, 1);
            }
        }
    }
```
*    **[⬆ Back to Top](#table-of-contents)**