# __Antipatterns__

## 1. Software Design Antipatterns

### 1.1 Abstraction inversion

Abstraction inversion is an antipattern that occurs in software design when a higher-level component depends on a lower-level component for its functionality, violating the principle of abstraction. This antipattern often results from a flawed design that fails to properly encapsulate the implementation details of lower-level components.

The Abstraction inversion antipattern can cause several issues, such as increased coupling between components, decreased modularity, and decreased maintainability. When higher-level components are dependent on lower-level components, any changes made to the lower-level components can have ripple effects on the higher-level components. This can lead to unexpected behavior, bugs, and difficulties in maintenance and testing.

One example of this antipattern is when a high-level module depends on low-level implementation details, such as specific data structures or algorithms, rather than abstract interfaces. This can make the high-level module less reusable and less adaptable to changes in the lower-level implementation.

To avoid the Abstraction inversion antipattern, it is important to design components with a clear separation of concerns, encapsulating implementation details behind well-defined interfaces. This approach promotes modularity, improves maintainability, and reduces coupling between components.

### 1.2 Ambigious viewpoint

The Ambiguous Viewpoint antipattern refers to a situation where a system or software design presents information from different perspectives, making it difficult for the user to understand which viewpoint is being presented at any given moment. This can lead to confusion and errors in interpretation.

For example, suppose a software application displays data from two different databases, but it does not clearly indicate which database the information is coming from. This can create ambiguity for the user, who may not be able to determine the source of the information or whether it is accurate.

To avoid this antipattern, it is important to clearly indicate the viewpoint or context of any information presented to the user. This can be achieved through consistent labeling, clear navigation, and appropriate use of visual cues and feedback. By providing a clear and unambiguous perspective, users can make more informed decisions and better understand the information presented to them.

### 1.3 Database-as-IPC

The Database-as-IPC antipattern refers to a design flaw in which a database is used as the primary means of communication between different components of a system. Rather than using appropriate communication protocols, such as message queues or APIs, components directly read and write to the database, effectively using it as an inter-process communication (IPC) mechanism.

This antipattern can lead to a number of problems. First, it can result in performance issues, as the database becomes a bottleneck for communication between components. Second, it can make the system more difficult to maintain and modify, as changes to the database schema can have cascading effects on other components. Finally, it can increase the likelihood of data inconsistencies and race conditions, as multiple components may be accessing and modifying the same data at the same time.

To avoid this antipattern, it is important to design systems with appropriate communication mechanisms in mind, and to use databases only for their intended purpose, such as storing and retrieving data.

### 1.4 Inner platform effect

The Inner-platform effect antipattern, also known as the Inner-platform syndrome, refers to a situation where a software development team creates a custom application framework or platform that is meant to provide a high level of abstraction and flexibility for building different types of applications. However, the framework or platform ends up being so complex and difficult to use that it becomes a platform in its own right, with its own set of bugs, limitations, and maintenance issues.

This antipattern often arises when a team tries to create a general-purpose platform that can support a wide range of use cases, but ends up making it too flexible and customizable, to the point where users must spend significant time and effort configuring it to their specific needs. As a result, the platform becomes overly complex and difficult to maintain, often leading to higher development costs and slower time-to-market.

To avoid the Inner-platform effect antipattern, it's important to strike a balance between flexibility and simplicity when creating a custom application framework or platform. Developers should focus on building a platform that is easy to use and maintain, while still providing the necessary level of abstraction and flexibility for building different types of applications. It's also important to thoroughly test the platform and ensure that it meets the needs of its users, without introducing unnecessary complexity or maintenance issues.

### 1.5 Input kludge

The "Input kludge antipattern" is a term used to describe a programming practice in which a programmer creates a complex input interface to solve a problem that could be easily addressed with simpler solutions. This antipattern usually results in an unnecessarily complex and difficult-to-use program.

For example, a programmer might create a graphical user interface (GUI) with multiple tabs, drop-down menus, and checkboxes to allow users to input data, when a simple command-line interface (CLI) would have sufficed. Another example would be creating a complicated form with numerous fields for a user to fill out, when a smaller number of fields could have achieved the same result.

The input kludge antipattern can lead to several negative consequences, including reduced usability, decreased efficiency, increased development time, and increased maintenance costs. Therefore, it is important for programmers to keep the input interface as simple and intuitive as possible while still meeting the project requirements.


### 1.6 Interface boat

The "Interface boat" antipattern is a software design problem that occurs when a class or interface becomes too large, complex, or unwieldy, resulting in decreased maintainability and flexibility. It is also sometimes referred to as the "God Interface" antipattern.

In this antipattern, a single interface or class is responsible for a wide range of functionality, often resulting in code that is difficult to modify and test. This can also lead to dependencies between different parts of the system, making it harder to isolate and fix bugs.

To avoid this antipattern, it's recommended to break down the interface or class into smaller, more focused components. This can improve modularity and make the code easier to understand, test, and maintain. Additionally, using a more modular design can also help to reduce dependencies and improve code reuse.


### 1.7 Magic Push-Button

The Magic Push-Button antipattern refers to the design flaw in a system or application where a single button or control is expected to perform a complex or multi-step operation without providing any feedback or context to the user. The button is often labeled with a generic or vague label such as "Do it" or "Go," and pressing it triggers a series of actions that may not be apparent to the user.

This antipattern can lead to confusion, frustration, and errors since users are not informed about what is happening behind the scenes or given an opportunity to confirm or modify the action. It can also be a security risk if the button initiates a critical operation without proper authentication or authorization.

Examples of the Magic Push-Button antipattern can be found in various contexts, such as software installation wizards, online checkout processes, and email applications. To avoid this antipattern, designers should provide clear and concise information about the action that will be taken, break down complex processes into manageable steps, and offer confirmation or review options before executing the action.


### 1.8 Race Hazzard

The "Race Hazard" anti-pattern refers to a situation where the outcome of a concurrent execution depends on the relative timing or ordering of events, and where this timing cannot be guaranteed or predicted in advance.

This can result in unpredictable behavior and bugs, as the outcome of the program may vary depending on factors outside of the programmer's control, such as the speed of different processors, the number of threads, or the scheduling policy of the operating system.

Examples of race hazards can include deadlocks, data corruption, or incorrect results. To avoid this anti-pattern, it is important to use proper synchronization mechanisms, such as locks, semaphores, or message passing, to ensure that different threads or processes do not interfere with each other's execution. Additionally, it can be helpful to use testing techniques such as stress testing or randomized testing to identify and eliminate race hazards before they become problems in production.


### 1.9 Stovepipe system

The "Stovepipe System" anti-pattern refers to a software architecture in which different components or modules of a system are developed independently of each other, with little or no integration or communication between them. Each component operates in its own silo, with its own data formats, interfaces, and business logic.

This can result in a lack of flexibility, scalability, and maintainability, as any changes or updates to the system must be made separately in each component, leading to duplication of effort and a high risk of errors or inconsistencies. It can also make it difficult to share data or functionality between different parts of the system, leading to inefficiencies and reduced performance.

To avoid this anti-pattern, it is important to design systems with a modular and integrated architecture, where different components can communicate and share data through standardized interfaces and protocols. This can be achieved through the use of service-oriented architectures, microservices, or other design patterns that promote loose coupling and modularity. Additionally, it can be helpful to establish clear communication and collaboration channels between different teams or departments working on the same system, to ensure that everyone is working towards the same goals and following the same standards and guidelines


## 2. OOP Antipatterns


### 2.1 Anemic domain model

Anemic domain model is an anti-pattern in software development where the domain model in an object-oriented program is designed to only contain data structures and basic accessors, without any significant business logic or behavior. This approach often results in a system where most of the business logic is placed in external services, rather than being part of the domain model itself.

The term "anemic domain model" was coined by Martin Fowler in his book "Patterns of Enterprise Application Architecture". According to Fowler, anemic domain models are problematic because they violate the principles of object-oriented programming, such as encapsulation and the use of behavior-rich objects. An anemic domain model can lead to several issues, including:

- Increased coupling: An anemic domain model often leads to a system where the domain objects are tightly coupled with external services, which can make the system more difficult to maintain and change.

- Reduced code reuse: Anemic domain models tend to have less reusable code, as the business logic is scattered across multiple services rather than being contained within the domain objects.

- Reduced maintainability: With business logic spread across multiple services, an anemic domain model can be harder to understand, modify and maintain.

In summary, an anemic domain model is an anti-pattern because it undermines the principles of object-oriented programming and can lead to several problems in software development, such as increased coupling, reduced code reuse, and reduced maintainability.


### 2.2 Call super
### 2.3 Circle-elipse problem
### 2.4 circular dependency
### 2.5 constant interface
### 2.6 God Object
### 2.7 Object cesspool
### 2.8 Object orgy
### 2.9 poltegeists
### 2.10 Sequential coupling
### 2.11 Singleton Pattern
### 2.12 Yo-Yo problem

## 3. Programming Antipatterns
### 3.1 Accidental complexity
### 3.2 Action at a distance
### 3.3 Boat anchor
### 3.4 Busy waiting
### 3.5 Caching failure
### 3.6 Cargo cult programming
### 3.7 Coding by Exception 
### 3.8 Error Hiding
### 3.9 Hard code
### 3.10 Lasagna code
### 3.11 Lava flow
### 3.12 Loop Switch sequence
### 3.13 Magic Numbers
### 3.14 Magic Strings
### 3.15 Repeating yourself
### 3.16 Shooting the messenger 
### 3.17 Shotgun surgery
### 3.18 Shotgun surgery
### 3.19 Soft code
### 3.18 Spagheti code

## 4. Methodological Antipatterns
### 4.1 Copy & Paste programming
### 4.2 Golden hammer
### 4.3 Invented here
### 4.4 Not invented here
### 4.5 Premature optimization
### 4.6 Programming by permutation
### 4.7 Reinventing the square wheel
### 4.8 Silver bullet
### 4.9 Test driven development

## 5. Cofiguration management Antipatterns
### 5.1 Dependency hell
Dependency hell is a colloquial term for the frustration of some software users who have installed software packages which have dependencies on specific versions of other software packages. The dependency issue arises when several packages have dependencies on the same shared packages or libraries, but they depend on different and incompatible versions of the shared packages. If the shared package or library can only be installed in a single version, the user may need to address the problem by obtaining newer or older versions of the dependent packages. This, in turn, may break other dependencies and push the problem to another set of packages.

### 5.2 DLL hell
A form of dependency hell occurring on Microsoft Windows.

### 5.3 Extension conflict
A form of dependency hell occurring on the classic Mac OS.

### 5.4 JAR Hell
A form of dependency hell occurring in the Java Runtime Environment before build tools like Apache Maven solved this problem in 2004.
