| Concept | Lua | TypeScript | JavaScript |
|---------|-----|------------|------------|
| **Variables** | `local name = "John"` | `let name: string = "John";` | `let name = "John";` |
| **Constants** | `local PI = 3.14` | `const PI: number = 3.14;` | `const PI = 3.14;` |
| **Functions** | `function greet(name) --[[...]] end -- @param name string` | `function greet(name: string): string { /* ... */ }` | `function greet(name) { /* ... */ }` |
| **If Statement** | `if age > 18 then --[[...]] end` | `if (age > 18) { /* ... */ }` | `if (age > 18) { /* ... */ }` |
| **For Loop (Numeric)** | `for i = 1, 5 do --[[...]] end` | `for (let i = 1; i <= 5; i++) { /* ... */ }` | `for (let i = 1; i <= 5; i++) { /* ... */ }` |
| **For Loop (Generic)** | `for key, value in pairs(table) do --[[...]] end` | `for (let key in object) { let value = object[key]; /* ... */ }` | `for (const [key, value] in Object.entries(object)) { }` *Key should always be const* |
| **While Loop** | `while condition do --[[...]] end` | `while (condition) { /* ... */ }` | `while (condition) { /* ... */ }` |
| **Switch Statement** | *Lua does not have a switch statement; use if-elseif-else instead.* | `switch(expression) { case value1: /* ... */ break; default: /* ... */ }` | `switch(expression) { case value1: /* ... */ break; default: /* ... */ }` |
| **Go To Statement** | `::label:: --[[...]] goto label` | *TypeScript does not support goto statements.* | *JavaScript does not support goto statements.* |
| **Arrays** | `local numbers = {1, 2, 3}` | `let numbers: number[] = [1, 2, 3];` | `let numbers = [1, 2, 3];` |
| **Objects** | `local person = { name = "John", age = 30 }` | `let person: { name: string; age: number; } = { name: "John", age: 30 };` | `let person = { name: "John", age = 30 };` |
| **Class** | *Lua does not have classes but can mimic them using tables.* | `class Person { name: string; constructor(private name: string) {} greet(): string { return "Hello, " + this.name; } }` | `class Person { constructor(name) { this.name = name; } greet() { return "Hello, " + this.name; } }` |
| **Inheritance** | *Lua does not have built-in inheritance but can implement it using metatables.* | `class Employee extends Person { department: string; constructor(name: string, department: string) { super(name); this.department = department; } }` | `class Employee extends Person { constructor(name, department) { super(name); this.department = department; } }` |
| **Modules** | *Lua modules are files that return a table.* | *TypeScript modules are files with exported functions, classes, etc.* | *JavaScript modules are files with exported functions, classes, etc.* |
| **Interfaces** | *Lua does not have a direct equivalent to TypeScript interfaces. Tables can be used for similar purposes.* | `interface Person { name: string; age: number; }` | *JavaScript does not have interfaces. Object shapes are often enforced through JSDoc comments or implied by object literals.* |
| **Defining Types** | *Lua is dynamically typed and does not have a mechanism for explicitly defining types.* | <code>type ID = string &#124; number;</code> | *JavaScript is dynamically typed; specific types are not defined, but type checking can be enforced with tools like JSDoc.* |
| **Using Types** | *In Lua, types are inferred and not explicitly defined.* | `let id: ID = "1234"; // ID can be a string or a number` | `let id = "1234"; // Type is inferred and can be string, number, etc.` |
| **Math Operations** | `math.sqrt(16)`<br>`math.floor(3.14)` | `Math.sqrt(16)`<br>`Math.floor(3.14)` | `Math.sqrt(16)`<br>`Math.floor(3.14)` |
| **JSON Parse/Stringify** | `json = require('dkjson')`<br>`local obj = json.decode('{"name":"John"}')`<br>`local str = json.encode(obj)` | `let obj = JSON.parse('{"name":"John"}');`<br>`let str = JSON.stringify(obj);` | `let obj = JSON.parse('{"name":"John"}');`<br>`let str = JSON.stringify(obj);` |
| **Type Checking** | `if type(x) == "number" then --[[...]] end` | `if (typeof x === "number") { /* ... */ }` | `if (typeof x === "number") { /* ... */ }` |
| **Random Numbers** | `math.random()`<br>`math.random(1, 10)` | `Math.random()`<br>`Math.floor(Math.random() * 10) + 1` | `Math.random()`<br>`Math.floor(Math.random() * 10) + 1` |
| **Round Numbers** | `math.floor(num + 0.5)` | `Math.round(num)` | `Math.round(num)` |
| **Trigonometry** | `math.sin(angle)`<br>`math.cos(angle)`<br>`math.tan(angle)` | `Math.sin(angle)`<br>`Math.cos(angle)`<br>`Math.tan(angle)` | `Math.sin(angle)`<br>`Math.cos(angle)`<br>`Math.tan(angle)` |
| **Exponential and Logarithm** | `math.exp(x)`<br>`math.log(x)` | `Math.exp(x)`<br>`Math.log(x)` | `Math.exp(x)`<br>`Math.log(x)` |
| **Defining a Vector** | `local vec = {x = 10, y = 20}` | `let vec: {x: number; y: number;} = {x: 10, y: 20};` | `let vec = {x: 10, y: 20};` |
| **Vector Addition** | `function addVec(v1, v2) return {x = v1.x + v2.x, y = v1.y + v2.y} end` | `function addVec(v1: {x: number; y: number;}, v2: {x: number; y: number;}): {x: number; y: number;} { return {x: v1.x + v2.x, y: v1.y + v2.y}; }` | `function addVec(v1, v2) { return {x: v1.x + v2.x, y: v1.y + v2.y}; }` |
| **Vector Magnitude** | `function vecMag(v) return math.sqrt(v.x^2 + v.y^2) end` | `function vecMag(v: {x: number; y: number;}): number { return Math.sqrt(v.x * v.x + v.y * v.y); }` | `function vecMag(v) { return Math.sqrt(v.x * v.x + v.y * v.y); }` |
| **Normalizing a Vector** | `function normalize(v) local mag = vecMag(v) return {x = v.x / mag, y = v.y / mag} end` | `function normalize(v: {x: number; y: number;}): {x: number; y: number;} { const mag = vecMag(v); return {x: v.x / mag, y: v.y / mag}; }` | `function normalize(v) { const mag = vecMag(v); return {x: v.x / mag, y: v.y / mag}; }` |

Note: This comparison is a high-level overview and does not cover every aspect of each language. Lua, TypeScript, and JavaScript each have unique features and nuances that may not have direct equivalents in the other languages. JavaScript's syntax and behavior can be similar to TypeScript's in many aspects, but TypeScript introduces static typing and some additional features not present in JavaScript.

| FiveM Function  | Lua Usage | TypeScript Usage | JavaScript Usage |
|---------|-----------|------------------|------------------|
| **AddEventHandler** | `AddEventHandler('eventName', function(args) --[[...]] end)` | `on('eventName', (args: ArgType) => { /* ... */ });` | `on('eventName', function(args) { /* ... */ });` |
| **RegisterNetEvent** | `RegisterNetEvent('eventName')` | `onNet('eventName', (args: ArgType) => { /* ... */ });` | `onNet('eventName', function(args) { /* ... */ });` |
| **RegisterServerEvent** | `RegisterServerEvent('eventName')` | `onNet('eventName', (args: ArgType) => { /* ... */ });` | `onNet('eventName', function(args) { /* ... */ });` |
| **TriggerEvent** | `TriggerEvent('eventName', args)` | `emit('eventName', args);` | `emit('eventName', args);` |
| **TriggerClientEvent** | `TriggerClientEvent('eventName', source, args)` | `emitNet('eventName', source, args);` | `emitNet('eventName', source, args);` |


***Please also note that mistakes can occur this is not meant to directly copy from for syntax, Please also note this is more so a tool to help while learning to and from each language.***

This project was made for a school project, Please note that I am not that invested and was purely meant to show that I am capable and able to make docs for .md readmes for github.
