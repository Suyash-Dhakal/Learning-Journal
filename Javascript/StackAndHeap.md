<h1>JavaScript Memory Management: Stack and Heap</h1>

<p>In JavaScript, memory management is abstracted away from the developer, but understanding the concepts of stack and heap memory can help in writing efficient code and diagnosing performance issues. This document provides an overview of stack and heap memory, their differences, and examples of their usage.</p>

<h2>Stack Memory</h2>

<p>Stack memory is used for static memory allocation. It is responsible for storing:</p>
<ul>
  <li><strong>Primitive Data Types</strong>: Such as <code>number</code>, <code>string</code>, <code>boolean</code>, <code>undefined</code>, and <code>null</code>.</li>
  <li><strong>Function Call Contexts</strong>: Includes local variables and the state of function calls.</li>
</ul>

<p><strong>Characteristics:</strong></p>
<ul>
  <li><strong>Fast Access</strong>: Stack memory operations are managed in a last-in, first-out (LIFO) manner.</li>
  <li><strong>Fixed Size</strong>: The size of stack memory is usually limited and predefined.</li>
  <li><strong>Automatic Management</strong>: Memory is automatically managed and cleaned up once the function scope ends.</li>
</ul>

<p><strong>Example:</strong></p>
<pre><code>
function example() {
    let a = 10; // 'a' is stored in stack memory
    let b = 20; // 'b' is stored in stack memory
    console.log(a + b);
}
example();
</code></pre>

<h2>Heap Memory</h2>

<p>Heap memory is used for dynamic memory allocation. It is responsible for storing:</p>
<ul>
  <li><strong>Objects</strong>: Includes complex data structures like objects, arrays, and functions.</li>
</ul>

<p><strong>Characteristics:</strong></p>
<ul>
  <li><strong>Dynamic Size</strong>: The heap is larger and can accommodate various sizes of data.</li>
  <li><strong>Manual Management</strong>: Memory management is handled by the JavaScript garbage collector.</li>
</ul>

<p><strong>Example:</strong></p>
<pre><code>
let obj = {
    name: "Alice",
    age: 30
}; // 'obj' is stored in heap memory

let arr = [1, 2, 3, 4, 5]; // 'arr' is stored in heap memory

function greet(person) {
    console.log(`Hello, ${person.name}!`);
}

greet(obj);
</code></pre>

<h2>Primitive vs Object Assignment</h2>

<p>Understanding the difference between primitive values and objects in terms of memory allocation and assignment:</p>

<ul>
  <li><strong>Primitive Values</strong>: Assignment creates a copy of the value. Changes to one variable do not affect others.</li>
</ul>

<p><strong>Example:</strong></p>
<pre><code>
let a = 10; // 'a' is assigned a value of 10
let b = a;  // 'b' is assigned a copy of the value of 'a', which is 10
b = 5;      // Changing 'b' to 5 does not affect 'a'

console.log(a); // Outputs: 10
console.log(b); // Outputs: 5
</code></pre>

<ul>
  <li><strong>Objects</strong>: Assignment copies the reference to the object. Changes made through one reference affect all references pointing to the same object.</li>
</ul>

<p><strong>Example:</strong></p>
<pre><code>
let obj1 = { name: "Suyash", age: 21 }; // 'obj1' is an object stored in heap memory
let obj2 = obj1; // 'obj2' is assigned a reference to the same object as 'obj1'

obj2.name = "Hari"; // Modifying the 'name' property of 'obj2' also affects 'obj1'

console.log(obj1.name); // Outputs: Hari
console.log(obj2.name); // Outputs: Hari
</code></pre>

<p>This document provides an overview of how stack and heap memory work in JavaScript, and how primitives and objects are managed differently in terms of memory allocation and assignment.</p>
