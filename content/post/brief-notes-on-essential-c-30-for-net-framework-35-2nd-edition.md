+++
title = "Brief Notes on Essential C# 3.0: For .NET Framework 3.5 (2nd Edition)"
description = "Notes on Mark Michaelis' Essential C# 3.0: For .NET Framework 3.5 (2nd Edition)."
draft = false
comments = true
date = "2008-08-16T08:45:00-05:00"
modified = "2008-08-29T22:15:22-05:00"
slug = "Brief-Notes-on-Essential-C-30-For-NET-Framework-35-2nd-Edition"
blogengine = "398b401c-9c20-4447-a6b1-45d8dcdfd41d"
categories = ["article", "technology"]
tags = [".net", "microsoft", "c#"]
+++

<p>
I&#39;ll be updating this as I read, but the date/time of the post will remain the same. This will by no means make up for a reading of the book&nbsp;- <a href="http://www.amazon.com/gp/product/0321533925?tag=strivinglifen-20" target="_blank">Essential C# 3.0: For .NET Framework 3.5 (2nd Edition)</a>. (Link to my review will be posted once I finish the book.) 
</p>
<div class="note">
<p>
I work primarily on the Web, so that will be my main focus from reading this book. Some chapters may not be present here, depending upon what I think is note-worthy at the time. 
</p>
</div>
<h3>Chapter 1</h3>
<p>
<strong>Immutable</strong> - strings are immutable in that when you reassign the variable, it points to a new location in memory. 
</p>
<p>
XML delimited comments are /** comment **/ and /// comment (wasn&#39;t aware of the first one). 
</p>
<h3>Chapter 21</h3>
<p>
<strong>Common Language Infrastructure (CLI)</strong> is an <em>international standard</em> containing the specifications for the <strong>Common Intermediate Language (CIL)</strong> and the runtime. 
</p>
<ol>
	<li>
	<div>
	C# compiler generates to Common Intermediate Language (CIL). (This is what other supported languages, like VB, J#, etcetera, are converted to as well.) 
	</div>
	</li>
	<li>
	<div>
	Generally at execution time (although you can do this earlier, on the machine that will actually run the code - NGEN) code is compiled from CIL to machine code. This is done by the just-in-time (JIT)&nbsp;compiler. 
	</div>
	</li>
	<li>
	<div>
	Now the C# code execution is managed by the Virtual Execution System (VES) / runtime. &quot;The runtime is responsible for loading and running programs and providing additional services (security, garbage collection, and so on) to the program as it executes.&quot; 
	</div>
	<ul>
		<li>
		<div>
		Managed code: &quot;the code that executes under the context of an agent such as the runtime&quot; Allows for additional services to be injected into a program 
		</div>
		</li>
		<li>
		<div>
		Managed execution: &quot;the process of executing under control of the runtime&quot; 
		</div>
		</li>
		<li>
		<div>
		Managed data: control over the allocation and deallocation of memory for the data 
		</div>
		</li>
	</ul>
	</li>
	<li>
	<div>
	Common Language Runtime (CLR) is &quot;the Microsoft-specific implementation of the runtime for the .NET platform.&quot; 
	</div>
	</li>
</ol>
<h4>Garbage collection</h4>
<p>
Built-in to the runtime. Does not happen at pre-determined or set times. Less likely to run &quot;if memory on the computer is still largely untapped.&quot; 
</p>
<p>
In .NET, &quot;objects that have lived for only a short period will be cleaned up sooner than objects that have already survived garbage collection sweeps.&quot; 
</p>
<p>
Objects that remain are compacted together, which &quot;often results in faster instantiation of new objects.&quot; 
</p>
<h3>Chapter 2&nbsp;</h3>
<p>
<strong>static</strong> methods must have a prefix of the type. text = string.Format(); 
</p>
<p>
<strong>instance</strong> methods instead prefix with the variable or instance name. firstName.ToUpper(); 
</p>
<p>
String immutability: text.ToUpper(); creates a new string that would need to be saved or used directly. 
</p>
<p>
System.Text.StringBuilder, however, modifies the data in the variable, and does not return a new string. 
</p>
<p>
<strong>Reference types</strong>: &quot;contains a pointer, an address, or a reference to a location in memory that is different from where the actual data resides.&quot; (For example, strings. Covered in&nbsp;Chapter 5.) <strong>Null</strong> can only be assigned to a reference type, unless you use the nullable modifier. For example, int? count = null;.&nbsp; 
</p>
<p>
string faxNumber; != string faxNumber = null; - in the latter case, the variable has been set. 
</p>
<p>
<strong>void</strong>: Don&#39;t expect any data. There is no data type. 
</p>
<p>
<strong>var</strong> was added in C# 3.0 to support anonymous types - types declared dynamically. Implicitly defined by what the compiler determines. Allows for &quot;joining (associating) data types or reducing the size of a particular type down to fewer data elements.&quot; (See pg 54-5 for example.) 
</p>
<h4>Categories of types</h4>
<ul>
	<li>
	<div>
	Value types: 
	</div>
	<ul>
		<li>
		<div>
		memory: data is stored on the stack 
		</div>
		</li>
		<li>
		<div>
		store the data 
		</div>
		</li>
		<li>
		<div>
		each variable gets its own place in memory 
		</div>
		</li>
	</ul>
	</li>
	<li>
	<div>
	Reference types: 
	</div>
	<ul>
		<li>
		<div>
		memory: data is stored on the heap 
		</div>
		</li>
		<li>
		<div>
		store the reference to where the data is stored, not the actual value 
		</div>
		</li>
	</ul>
	</li>
</ul>
<p>
<strong>Stack and heap</strong>: See Figure 2.2 on page 57.&nbsp; 
</p>
<h4>Casting</h4>
<p>
(type) for explicit casting. Parse() for string to numeric. System.Convert for number types to other base types. TryParse() as of C# 2.0 (returns false instead of throwing an exception). 
</p>
<p>
All types support ToString(): if the type has an explicit implementation the string representation of the data is returned, otherwise the name of the data type is. 
</p>
<h4>Arrays</h4>
<p>
Page 65-80.&nbsp; 
</p>
<p>
&quot;<strong>Arrays</strong> provide a means of declaring a collection of data items that are of the same type using a single variable.&quot; 
</p>
<p>
string[] languages; 
</p>
<p>
Use commas for additional dimensions: string[,] cells; 
</p>
<p>
Assigning after declaring requires <strong>new</strong>. (new: &quot;tells the runtime to allocate memory for the data type&quot;) 
</p>
<p>
Jagged array: array of arrays. Page 70. Length returns number of elements in the outside/first array. 
</p>
<p>
Arrays have a fixed length, so can&#39;t be changed without re-creating the array. For multi-dimensional, it&#39;s the number of elements total. 
</p>
<p>
Array is reference type - use Clone() method for a new copy. 
</p>
<p>
Common errors 79-80. 
</p>
<h3>Chapter 3&nbsp;</h3>
<p>
Constants (const)&nbsp;are&nbsp;evaluated and determined at compile time.&nbsp; 
</p>
<p>
for loops can consist of multiple subexpressions (see page 124), although generally you shouldn&#39;t. 
</p>
<p>
In a foreach loop, the identifier (foreach(type identifier in collection)) is read-only. 
</p>
<p>
C# preprocessor directives listed on page 136. 
</p>
<h3>Chapter 4&nbsp;</h3>
<p>
To the compiler, the namespaces System.Collections and System.Collections.Generics are at the same level. Hierarchy implications are for human-readability only. In fact, namespaces are nested, which basically means that in using statements, you still have to&nbsp;use System.Text, even if you&#39;re using System. 
</p>
<p>
&#39;All types are compatible with the data type object.&#39; 
</p>
<p>
Over time, look for ways to simplify your code by refactoring - moving blocks of code into methods. 
</p>
<p>
Alias using by way of using namespaceAlias = namespace. For example, using CountDownTimer = System.Timers.Timer; 
</p>
<p>
<strong>Command-line arguments</strong> covered on 165-6. 
</p>
<p>
When passing parameters, whether they be reference or value types, the original variables are not changed (value is passed, not the reference). However, if you add <strong>ref</strong> before the parameters (for both method and call), they can be. See 169. 
</p>
<p>
See 170-1 for output parameters (<strong>out</strong>). 
</p>
<p>
<strong>Parameter arrays</strong> covered on 172-4. 
</p>
<p>
<strong>Common exception types</strong> listed on 187-8. 
</p>
<p>
Avoid throwing exceptions for known errors or conditions. 
</p>
<h3>Chapter 5&nbsp;</h3>
<p>
OOP on 196-9, 202, 214. 
</p>
<p>
An <strong>object</strong> is an instance of a <strong>class</strong>, which is a template for&nbsp;an object.&nbsp; 
</p>
<p>
Instance fields (no static modifier) can only be accessed from an instance of the class (an object). 
</p>
<p>
this is an implicit field within every class that returns an instance of the object itself. See 206-7. 
</p>
<p>
<strong>public</strong> access modifier means&nbsp;field is available outside of class, while <strong>private</strong> is the opposite (and the default). 
</p>
<p>
Use <strong>properties</strong> to modify private fields. 
</p>
<p>
public <em>type</em> <em>Property</em> {<br />
&nbsp;&nbsp; get { return&nbsp;_;}<br />
&nbsp;&nbsp; set { _ = value;}<br />
} 
</p>
<p>
It&#39;s a good idea to use properties within the class as well, since validation can take place in one area only. 
</p>
<p>
Remove get and/or set for write- and/or read-only. 
</p>
<p>
Access modifier (public, private, ...)&nbsp;can be applied to get or set, but <em>only</em> on one. 
</p>
<p>
Properties can be virtual fields - for example, Employee.Name could be FirstName + &quot; &quot; + LastName. 
</p>
<p>
Properties and methods cannot be ref or out parameter values. Copy to a variable first, pass that, and pass variable back to property. 
</p>
<p>
<strong>Constructors</strong> are methods with no return types, with a name identical to class name, that allow fields to be initialized. 
</p>
<p>
<strong>Default constructor</strong>, taking no parameters, is created by the C# compiler at compilation, unless a costructor is declared. If you want a default one&nbsp;- Employee() for example, after you&#39;ve added Employee(FirstName, LastName) - you&#39;ll have to add it yourself. 
</p>
<p>
Object initializers on 232. 
</p>
<p>
<strong>Overloading constructors</strong> involves different number or types of parameters. Use constructor initializers to eliminate code duplication by calling other constructors, using this. See 235. 
</p>
<p>
Even better, possibly use a private method to <strong>Initialize()</strong> properties/object? See 236-7. 
</p>
<p>
<strong>Anonymous types</strong> covered on 237-9. 
</p>
<p>
<strong>static</strong> fields are shared across multiple instances of an object, and belong to the class (not the instance). See 240-241 for examples. 
</p>
<p>
&quot;In designing objects, programmers should take care to declare both fields and methods appropriately as static or instance-based.&nbsp;In general, you should declare [...]&nbsp;methods that access instance data (where the instance is not passed in as a parameter) as instance methods. Static fields store data corresponding to the class [...] Instance fields store data associated with the object.&quot; (243) 
</p>
<p>
<strong>static constructors</strong> are called by the runtime upon first access to the class. See 245. 
</p>
<p>
Better to have&nbsp;a static property than a public static field (246). 
</p>
<p>
<strong>static classes</strong> can&#39;t be instantiated, but usually don&#39;t need to be (objects would be pointless). See 247-8, which involves math. These classes also can&#39;t be extended (they&#39;re marked as sealed). 
</p>
<p>
It&#39;s possible to add instance methods to any class using <strong>extension methods</strong>. However, use these sparingly, since there&#39;s typically a better way. See 249-50. 
</p>
<p>
<strong>const fields</strong> are automatically static. 
</p>
<p>
<strong>readonly fields</strong> declare &quot;that the field value is modifiable only from inside the constructor or directly during declaration,&quot; so they can vary and change instance to instance.&nbsp;See 251-2. 
</p>
<p>
<strong>Nested classes</strong> are classes defined within another class. Allow for the private modifier, and are rare. See 253-4. 
</p>
<p>
<strong>Partial classes</strong> allow one class to be defined in multiple files (such as a nested class in another file). 
</p>
<p>
<strong>Partial methods</strong> are also allowed, as long as they return void (partial void Class). See 256-9. 
</p>
<h3>Chapter 6&nbsp;</h3>
<p>
When defining a <strong>derived class</strong> - methods defined on the base class are avilable to all subclasses - use a colon followed by the base class. This inheritence follows all the way down, to an unlimited numder of subclasses from subclasses from base classes. 
</p>
<p>
Derived&nbsp;classes can be&nbsp;cast to the base class, implicitly.&nbsp;However, the reverse is not true. 
</p>
<p>
Private members are not available to derived classes, while <strong>protected</strong> members are only available to derived classes. 
</p>
<p>
While you can only derive from one base class in C#, you can work around this, if necessary, by using <strong>aggregation</strong>, by calling an instance of the second class you wish to derive from. 
</p>
<p>
<strong>sealed</strong> classes cannot be derived from. You can assign these on base as well as derived classes (so that no further derivations are possible). 
</p>
<p>
By using the <strong>virtual</strong> modifier in&nbsp;the base class&nbsp;and <strong>override</strong> in the&nbsp;derived classes, instance methods and properties can be overriden. Fields and static members cannot be overriden. Override implies virtual (unless you&#39;ve used <strong>override sealed</strong>). 
</p>
<p>
Be careful when allowing methods to be overriden, as the most derived implementation will be used, so keep core functionality non-virtual. See 276-7 for one such way. 
</p>
<p>
Use <strong>new</strong> to break out of the above. See 280-1 for something of an example. 
</p>
<p>
Use <strong>base</strong>.Method() to use the base classes&#39; method. Useful for when derived class &#39;extends&#39; the method in some way. See 282-3 for a good example (ToString()). 
</p>
<p>
If the base class has no default constructor (ClassName()), this must be defined in the derived class constructor. See 284. 
</p>
<p>
<strong>abstract</strong> classes are available for derivation only. They typically define what derived classes should contain, methods or properties, but not how to implement them. Abstract implies virtual. 
</p>
<p>
See 286-7, 289-90 for an example. 
</p>
<p>
Since everything derives from System.Object, there are methods that are available on everything. See 290-1 for these (ToString() is one, which allows for 33.ToString()). 
</p>
<p>
Use <strong>is</strong> to check what the underlying type is. See 292. Use <strong>as</strong> to attempt to convert to a type, and assign null if the conversion fails. 
</p>
<h3>Chapter 7</h3>
<p>
Interfaces allow common method signatures across classes, with different functionality, and&nbsp;without inheritence. You can therefore switch implementations without changing the calling code. See 297. 
</p>
<p>
Method declarations are followed by a semi-colon, not curly braces, and properties must be used instead of fields. The interface has no implementation, no actual code nor fields. All members are public, and cannot&nbsp;be declared as such or otherwise (no access modifiers). 
</p>
<p>
Classes can implement multiple interfaces, and are listed after the class name, along with the base class (if any). 
</p>
<p>
If a class&nbsp;uses an interface, all members of the interface must be implemented. Throw NotImplementedException as needed. 
</p>
<p>
Choosing between an explicit and implicit interface implementation covered on 306-7. If in doubt, use explicit. 
</p>
<p>
Multiple interface inheritance example on page 310. 
</p>
<p>
Changing an interface can be intensive, as all classes that implement the interface must also change. See 316-7 for an example of a version-safe way. 
</p>
<p>
See 318 for a comparison of abstract classes with interfaces. 
</p>
<h3>Chapter 8</h3>
<p>
Reminder: types are either reference types or value types.
</p>
<p>
<strong>Value types</strong> directly contain their value, and point to a location in memory, so each new value type, or using a value type within a method,&nbsp;means more memory usage. These derive from System.ValueType.
</p>
<p>
<strong>Reference types</strong> store the reference / memory address of the value, not the value itself. This means that two variables can point to the same reference, and therefore changing one would change the other.
</p>
<p>
<strong>string</strong> and <strong>object</strong> are reference types, the rest of the primitive types are value types.
</p>
<p>
Use <strong>struct</strong> to create a custom value type. Example on 324-5. See initialization rules on 326.
</p>
<p>
Boxing/unboxing content on 329-35, which seems to be out of place here (went over the head).
</p>
<p>
Use <strong>enum</strong> to create a set of values, with each value having a name. See 335-40. Use singular when declaring.
</p>
<p>
To combine enums, use&nbsp;a plural name. See 340-4 for additional details on doing this.
</p>
<p>
&nbsp;
</p>
<h3>Reading log</h3>
<p>
(If you&#39;re interested, otherwise, since I&#39;m reading the electronic version of the book, I need someplace to keep track of this.) 
</p>
<ul>
	<li>
	<div>
	08/15/2008: &gt; xlvi 
	</div>
	</li>
	<li>
	<div>
	08/16/2008: 1 &gt; 30, 749 &gt; 770, 31 &gt; 82, 83 &gt; 146 
	</div>
	</li>
	<li>
	<div>
	08/21/2008: 147 &gt; 194 
	</div>
	</li>
	<li>
	<div>
	08/23/2008: 195 &gt; 260 
	</div>
	</li>
	<li>
	<div>
	08/24/2008: 261 &gt; 294 (re-read at some point) 
	</div>
	</li>
	<li>
	<div>
	08/29/2008: 295 &gt; 320 (need to re-read), 320 &gt; 346 (also need to re-read)
	</div>
	</li>
</ul>

