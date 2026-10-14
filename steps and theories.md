# LOCALSOCIAL: Complete Development Roadmap

## 1. First, understand the final product

**LocalSocial — Local Business Growth & Customer Retention System**

The application will help local businesses manage customer relationships, track visits, reward loyal customers, identify inactive customers, and organize marketing campaigns.

For example, imagine a gym with 500 customers.

The owner should be able to:

* Register and manage customers.
* Track their visits and purchases.
* Award and redeem loyalty points.
* Identify frequent and inactive customers.
* Create campaigns targeting particular customer groups.
* View business statistics.
* Save all records and access them later.

We'll initially build a single-business application. Multi-business support can be added later if the core system is stable.

### Our technology stack

| Component               | Technology        | Purpose                                          |
| ----------------------- | ----------------- | ------------------------------------------------ |
| Programming language    | C++               | Business logic and OOP implementation            |
| Frontend                | HTML              | Interface structure                              |
| Styling                 | CSS               | Visual design                                    |
| Frontend interactions   | JavaScript        | Forms, tables, navigation, and API communication |
| Backend interface       | HTTP API          | Communication between frontend and C++           |
| Initial storage         | Text files or CSV | Persistent records                               |
| Version control         | Git and GitHub    | Track development progress                       |
| Development environment | VS Code           | Write, compile, and test the application         |

We will not introduce a database server, AI integration, or messaging APIs until they are genuinely needed.

---

# PHASE 1 — APPLICATION FOUNDATION

## Step 1. Project setup and planning

**Objective:** Establish the development environment and define the application's structure.

### What you need to do

1. Create the `LocalSocial` project folder.
2. Open it in VS Code.
3. Create separate folders for the backend, frontend, data, and documentation.
4. Verify that your C++ compiler works.
5. Verify that you can compile and execute a simple C++ program.
6. Initialize a Git repository.
7. Create a README describing the project.

### What belongs in `main.cpp` at this stage?

Initially, `main.cpp` should have just one responsibility: **start the application**.

It should:

* Provide the program's entry point.
* Display the LocalSocial startup information.
* Confirm that the program has started.
* End successfully.

Do not put customer management, authentication, loyalty calculations, or campaign logic in it yet.

### Concepts to understand

* What a C++ program is.
* The purpose of the `main()` function.
* Compilation versus execution.
* Header files versus source files.
* Project directory organization.
* Basic Git operations.

### Milestone 1

**The application compiles and runs successfully on your computer.**

You should be able to explain how the compiler turns your C++ source file into an executable program.

---

## Step 2. Design the main application flow

**Objective:** Decide how users will navigate LocalSocial.

Before implementing features, we need to define the application's control flow.

The first version will follow this sequence:

1. Start the application.
2. Display the welcome screen.
3. Display the login option.
4. Authenticate the user.
5. Display the main dashboard or menu.
6. Let the user select a module.
7. Perform the requested operation.
8. Return to the dashboard.
9. Save changes when appropriate.
10. Exit safely.

### What will `main.cpp` do now?

It will gradually become the application's entry point and coordinator.

Its responsibilities will be limited to:

* Starting the application.
* Initializing the necessary components.
* Starting the main application flow.
* Coordinating high-level navigation.
* Handling application shutdown.

It should not contain the detailed implementation of every feature.

Think of `main.cpp` as the person directing a team, not the person doing every job.

### Concepts to understand

* Conditional statements.
* Loops.
* Functions.
* Switch statements.
* Menu-driven programming.
* Separation of responsibilities.

### Milestone 2

**A working console menu allows you to navigate between options and exit correctly.**

At this stage, the individual modules can still be placeholders.

We are testing the application's structure, not its business functionality.

---

# PHASE 2 — OBJECT-ORIENTED DESIGN

This is the most important phase for your OOP PBL.

## Step 3. Design the class architecture

**Objective:** Identify the objects that make up LocalSocial.

Before implementing classes, decide what information each object stores and what operations it performs.

Our initial class architecture will be:

| Class               | Responsibility                                            |
| ------------------- | --------------------------------------------------------- |
| `Person`            | Common personal information                               |
| `Customer`          | Customer identity, status, and customer-related behaviour |
| `VIPCustomer`       | Specialized customer benefits                             |
| `Business`          | Business profile and business information                 |
| `Visit`             | Customer visit records                                    |
| `Transaction`       | Purchase or payment records                               |
| `Reward`            | Information about available rewards                       |
| `LoyaltyProgram`    | Points, earning rules, and redemption                     |
| `Campaign`          | Common campaign properties and behaviour                  |
| `DiscountCampaign`  | Discount-based campaigns                                  |
| `RetentionCampaign` | Customer-retention campaigns                              |
| `Authentication`    | Login and credential verification                         |
| `FileManager`       | Loading and saving records                                |
| `Analytics`         | Business statistics and reports                           |

We can add, remove, or simplify classes when the detailed design reveals a better structure.

### What should you do?

For every class, write down four things:

1. What real-world entity does it represent?
2. What data does it own?
3. What operations should it perform?
4. Which other classes does it interact with?

For example, a `Customer` owns customer-specific information, while `LoyaltyProgram` manages the rules governing points and redemption.

The customer shouldn't need to know how the entire file-storage system works.

### Concepts to understand

* Classes and objects.
* Attributes and member functions.
* Class responsibilities.
* Object relationships.
* Association and composition.
* Encapsulation.
* Basic UML class diagrams.

### Milestone 3

**A documented class design and UML diagram that you can explain without looking at your notes.**

Do this before creating dozens of source files.

---

## Step 4. Build the `Person` class

**Objective:** Learn how to implement your first reusable class.

`Person` will represent the common information shared by people in the system.

Initially, it will contain:

* Name.
* Age.
* Phone number.

### What you will implement

* Data members.
* Public and private access.
* Member functions.
* Setters and getters.
* Input validation.
* Displaying person information.

You will create a header file for the class declaration and a source file for its implementation.

### Concepts to understand

**Encapsulation:** Protecting an object's internal state.

**Access modifiers:** Controlling which parts of the program can access class members.

**Member functions:** Operations associated with an object.

**Constructors:** Initializing objects when they are created.

**Validation:** Preventing invalid data from entering the system.

### Milestone 4

You can create a `Person` object, initialize its information, retrieve its data, and display it.

You should also understand why private data members are generally preferable to exposing all fields publicly.

---

## Step 5. Build the `Customer` class

**Objective:** Extend the class architecture to represent customers.

A customer is a person with additional customer-related information.

The class will manage:

* Customer ID.
* Registration date.
* Loyalty points.
* Customer status.
* Visit-related information or a reference to the relevant records.

We'll decide exactly where each responsibility belongs during implementation.

### What you will implement

* The `Customer` class.
* Inheritance from `Person`.
* Customer-specific member functions.
* Customer information validation.
* Customer identification.

### Concepts to understand

* Inheritance.
* Base classes and derived classes.
* Constructors in inheritance.
* Access control in inheritance.
* Function overriding.
* The difference between inherited data and newly introduced data.

### Milestone 5

You can create customers and explain how inheritance avoids duplicating common personal information.

---

# PHASE 3 — CORE BUSINESS FUNCTIONALITY

## Step 6. Build customer management

**Objective:** Make customer records usable.

This is the first major functional module.

### Features

1. Add a customer.
2. View all customers.
3. Search for a customer.
4. Update customer information.
5. Delete a customer.
6. Prevent duplicate customer IDs.
7. Validate customer details.

### Logic you must design

When a user registers a customer, the application must:

1. Collect the required information.
2. Validate the input.
3. Check whether the customer ID already exists.
4. Create a valid customer object.
5. Add it to the customer collection.
6. Confirm the operation.

Searching should return a meaningful result if the customer doesn't exist.

Deleting a customer should also account for related records. We must decide whether deletion is allowed when the customer has visit or transaction history.

### Concepts to understand

* `vector` and collections.
* Searching.
* Iteration.
* Function decomposition.
* Object storage.
* CRUD operations: Create, Read, Update, Delete.
* Input validation.
* Basic error handling.

### Milestone 6

You can register, search, update, display, and delete customers correctly.

Test the module with at least 10 sample customers before moving on.

---

## Step 7. Build business management

**Objective:** Store the business profile.

The `Business` class will initially manage:

* Business ID.
* Business name.
* Business category.
* Owner name.
* Contact details.

### Features

* Create a business profile.
* View the profile.
* Update business information.
* Validate the required fields.

### Logic

A customer belongs to the business's customer records. Business details should not be duplicated inside every customer object.

We will keep the first implementation focused on one business.

### Milestone 7

You can create and manage a business profile, and customer management operates within that business's context.

---

## Step 8. Build visit management

**Objective:** Track customer activity over time.

Create the `Visit` class.

A visit record should contain:

* Visit ID.
* Customer ID.
* Visit date.
* Optional visit purpose.

### Features

* Record a visit.
* Display visit history.
* View a customer's visits.
* Calculate visit totals.
* Reject visits associated with nonexistent customers.
* Prevent accidental duplicate records where applicable.

### Important design decision

The visit history should be the authoritative source for visit activity.

If the application maintains a separate total visit count in the customer record, we must keep it synchronized with the visit history.

Otherwise, the application could display incorrect statistics.

### Concepts to understand

* Object relationships.
* Collections of objects.
* Date representation.
* Data consistency.
* Validation across multiple classes.

### Milestone 8

You can record visits, view a customer's history, and calculate visit totals accurately.

---

## Step 9. Build purchase and transaction management

**Objective:** Track customer purchases where relevant.

This module can be simplified if your faculty expects a smaller PBL.

A `Transaction` record could contain:

* Transaction ID.
* Customer ID.
* Date.
* Amount.
* Transaction status.

### Features

* Record a purchase.
* View purchase history.
* Calculate total spending.
* Calculate average purchase value.
* Reject invalid amounts.
* Prevent duplicate transaction IDs.

### Why include this?

Visit frequency alone doesn't tell a business how much a customer spends.

Combining visits and purchase records allows the application to demonstrate more meaningful customer analysis.

### Milestone 9

You can calculate basic customer spending statistics from actual transaction records.

---

# PHASE 4 — LOYALTY AND CUSTOMER INTELLIGENCE

## Step 10. Build the loyalty program

**Objective:** Reward customer activity.

Create the `LoyaltyProgram` and `Reward` classes.

For the initial implementation, assume the following rules:

* One eligible visit earns 10 points.
* One reward costs 100 points.
* A customer cannot redeem more points than they possess.

These values are configurable examples, not universal business rules.

### Features

* Award points.
* View a customer's balance.
* Display available rewards.
* Redeem rewards.
* Reject invalid redemptions.
* Maintain a record of point changes.

### Logic

When awarding points, the application should verify that the visit is eligible for the reward.

When redeeming a reward, it should verify that the customer has sufficient points.

We also need to prevent duplicate processing from awarding the same visit's points twice.

### Concepts to understand

* Business rules.
* Encapsulation.
* Validation.
* State changes.
* Separation of responsibilities.
* Invariants, such as preventing negative point balances.

### Milestone 10

The loyalty system awards and redeems points correctly, and balances remain consistent after multiple operations.

---

## Step 11. Implement customer segmentation

**Objective:** Identify different groups of customers using recorded activity.

We'll initially define these segments:

| Segment           | Example rule                           |
| ----------------- | -------------------------------------- |
| New customer      | Registered within the last 7 days      |
| Frequent customer | At least 10 visits in the last 30 days |
| Inactive customer | No recorded visit in the last 30 days  |
| VIP customer      | Meets defined eligibility criteria     |

These are configurable starting rules.

### What you will implement

* Identify new customers.
* Identify frequent customers.
* Identify inactive customers.
* Identify VIP customers.
* Display the customers in each segment.

### Important distinction

VIP status and customer activity are not necessarily the same thing.

A customer might be inactive but still qualify as VIP because of historical spending.

Therefore, segmentation rules should be defined independently rather than treating every segment as mutually exclusive.

### Milestone 11

The system can identify customer segments using recorded data and clearly defined rules.

---

# PHASE 5 — OOP FEATURES AND CAMPAIGN MANAGEMENT

## Step 12. Implement abstraction and polymorphism

**Objective:** Demonstrate advanced OOP concepts through meaningful functionality.

This is where your project should show more than basic classes and CRUD operations.

### Customer hierarchy

We will use `Person`, `Customer`, and `VIPCustomer` to demonstrate inheritance where appropriate.

### Campaign hierarchy

The campaign system will have a base `Campaign` class and specialized campaign types.

For example:

* `DiscountCampaign`.
* `RetentionCampaign`.

The base class will define common campaign properties and operations.

The derived classes will implement their specialized behaviour.

### Concepts to demonstrate

| Concept                      | Application                                                   |
| ---------------------------- | ------------------------------------------------------------- |
| Encapsulation                | Protecting customer and loyalty data                          |
| Inheritance                  | `Person` and `Customer` hierarchy                             |
| Abstraction                  | Defining common campaign behaviour                            |
| Polymorphism                 | Executing different campaign types through a common interface |
| Function overriding          | Customizing campaign execution                                |
| Virtual functions            | Supporting runtime polymorphism                               |
| Constructors and destructors | Managing object initialization and cleanup                    |

**Important:** We won't add artificial classes just to tick boxes on an OOP checklist. Every major concept should have a clear purpose in the application.

### Milestone 12

You can demonstrate and explain the major OOP principles using actual LocalSocial functionality.

---

## Step 13. Build campaign management

**Objective:** Allow a business owner to create and simulate marketing campaigns.

### Features

1. Create a campaign.
2. Assign a campaign ID.
3. Choose a campaign type.
4. Select a target customer segment.
5. Define the campaign message.
6. Preview eligible customers.
7. Simulate execution.
8. Record execution statistics.

### Example workflow

A gym owner creates a retention campaign.

The application identifies customers with no recorded visit in the last 30 days.

The owner reviews the target list and executes the campaign in simulation mode.

The system records:

* Campaign ID.
* Campaign type.
* Target segment.
* Number of eligible customers.
* Number of selected recipients.
* Simulation status.

The system must not claim that messages were delivered because no external messaging service is connected.

### Concepts to understand

* Class hierarchies.
* Runtime polymorphism.
* Object interactions.
* Business rules.
* Customer filtering.
* State management.

### Milestone 13

You can create and execute simulated campaigns against actual customer segments.

---

# PHASE 6 — DATA PERSISTENCE

## Step 14. Implement file handling

**Objective:** Ensure records survive application restarts.

Without persistence, the application loses its records when the program closes.

Create a `FileManager` class responsible for storing and retrieving data.

### Data to persist

* Business profiles.
* Customers.
* Visits.
* Transactions.
* Loyalty records.
* Rewards.
* Campaigns.
* Campaign execution statistics.

### Features

* Save records.
* Load records when the application starts.
* Handle missing files.
* Handle malformed records.
* Avoid duplicate records when loading.
* Preserve relationships between customer IDs and their associated records.

### Important design decision

The application must load data in a controlled order.

For example, customer records should be available before visit records are validated against them.

We'll also define what happens when a file is missing or corrupted.

### Concepts to understand

* File streams.
* Reading and writing records.
* Serialization and deserialization.
* Delimiters and record formats.
* Error handling.
* Data integrity.

### Milestone 14

You can close LocalSocial, restart it, and recover the previously saved records without losing or duplicating data.

---

# PHASE 7 — ANALYTICS AND REPORTING

## Step 15. Build the analytics module

**Objective:** Convert stored records into useful business information.

Create an `Analytics` class.

### Reports

The application should calculate:

* Total customers.
* New customers.
* Frequent customers.
* Inactive customers.
* Total visits.
* Total spending.
* Average spending per customer.
* Loyalty points outstanding.
* Rewards redeemed.
* Campaigns created.
* Campaigns simulated.

### Logic

The analytics module should calculate its reports from the underlying records.

It should not maintain arbitrary hardcoded statistics.

For example, the total number of visits should be calculated from valid visit records rather than incremented independently in several unrelated modules.

### Milestone 15

All major reports display values derived from the actual application data.

You should be able to manually verify the results using a small sample dataset.

---

# PHASE 8 — WEB INTERFACE

Now we turn the working business system into a more polished application.

**We will build the interface in parallel with the backend once the core class structure is stable.** We won't wait until the entire backend is finished to begin frontend development.

This reduces integration risk and allows us to test the interface against working features as they become available.

## Step 16. Design the frontend

**Objective:** Create the visual structure of LocalSocial.

The frontend will contain these pages:

| Page              | Purpose                           |
| ----------------- | --------------------------------- |
| Login             | Authenticate the business owner   |
| Dashboard         | Display summary statistics        |
| Customers         | Manage customer records           |
| Customer Profile  | View visits, loyalty, and history |
| Visits            | Record and review visits          |
| Loyalty           | View points and rewards           |
| Campaigns         | Create and simulate campaigns     |
| Analytics         | Display reports                   |
| Business Settings | Manage business details           |

### What you will do

First, define the layout and navigation.

Then design the pages and their visual hierarchy.

Finally, implement the forms, tables, buttons, and interactions.

### Design principles

* Consistent typography.
* Clear navigation.
* Readable tables.
* Meaningful status indicators.
* Responsive layout.
* Useful error messages.
* No decorative metrics that do not correspond to real data.

### Milestone 16

All major pages exist, navigation works, and the interface is usable even before every backend integration is complete.

---

## Step 17. Connect the frontend to the C++ backend

**Objective:** Make the graphical interface operate on real application data.

The frontend cannot directly call arbitrary C++ classes running in a separate process.

We need an API between the two.

The initial architecture will be:

Frontend → HTTP request → C++ backend → Business logic → Storage.

The response returns to the frontend, which updates the displayed information.

### Features to connect

* Customer registration.
* Customer search and updates.
* Visit recording.
* Loyalty operations.
* Campaign creation.
* Analytics reports.

### Concepts to understand

* Client-server architecture.
* HTTP.
* API endpoints.
* Request and response formats.
* JSON.
* Error handling across application boundaries.

We will choose a suitable C++ HTTP framework when we reach this phase.

### Milestone 17

Actions performed through the interface change the backend's actual records, and the updated information appears in the interface.

---

# PHASE 9 — TESTING AND FINAL SUBMISSION

## Step 18. Integrate and test the entire application

**Objective:** Verify that the modules work together.

We will test a complete business workflow:

1. Start LocalSocial.
2. Log in.
3. Create a business profile.
4. Register customers.
5. Record customer visits.
6. Record transactions.
7. Award loyalty points.
8. Redeem rewards.
9. Generate customer segments.
10. Create a retention campaign.
11. Simulate campaign execution.
12. View analytics.
13. Save the records.
14. Restart the application.
15. Verify that the records remain correct.

### Edge cases to test

* Duplicate customer IDs.
* Invalid phone numbers.
* Negative purchase amounts.
* Missing customers.
* Invalid menu choices.
* Insufficient loyalty points.
* Duplicate visit processing.
* Missing storage files.
* Corrupted records.
* Campaigns with no eligible customers.

### Milestone 18

The core application works from beginning to end, and important failure cases are handled correctly.

---

## Step 19. Prepare the project documentation

Your PBL submission should explain the problem, design, implementation, and results.

Prepare:

1. Title page.
2. Abstract.
3. Problem statement.
4. Objectives.
5. Scope and limitations.
6. Hardware and software requirements.
7. System architecture.
8. UML class diagram.
9. Use-case diagram.
10. Flowchart.
11. Module descriptions.
12. OOP concepts demonstrated.
13. Implementation details.
14. Testing and results.
15. Screenshots.
16. Conclusion.
17. Future scope.
18. References.

### Milestone 19

Your documentation accurately reflects the implementation and is ready for submission.

---

## Step 20. Prepare for the viva

**Objective:** Be able to defend your design and implementation.

You should be prepared to explain:

* Why you created each major class.
* Why some members are private.
* Where inheritance is used and why.
* How polymorphism works in your campaign system.
* How customer records are stored.
* How file handling works.
* How duplicate records are prevented.
* How loyalty points are calculated.
* How customer segmentation works.
* How the frontend communicates with the backend.
* What the limitations of the current implementation are.

You should also be able to demonstrate the project without relying on a prerecorded video.

### Milestone 20

You can explain the architecture, demonstrate the major features, and answer technical questions about your implementation.

---

# Your complete milestone tracker

Here is the sequence to follow.

| Step | Milestone                               | Status      |
| ---- | --------------------------------------- | ----------- |
| 1    | Project setup and compiler verification | Not started |
| 2    | Main application flow                   | Not started |
| 3    | Class architecture and UML              | Not started |
| 4    | `Person` class                          | Not started |
| 5    | `Customer` class                        | Not started |
| 6    | Customer management                     | Not started |
| 7    | Business management                     | Not started |
| 8    | Visit management                        | Not started |
| 9    | Transaction management                  | Not started |
| 10   | Loyalty and rewards                     | Not started |
| 11   | Customer segmentation                   | Not started |
| 12   | Abstraction and polymorphism            | Not started |
| 13   | Campaign management                     | Not started |
| 14   | File persistence                        | Not started |
| 15   | Analytics and reports                   | Not started |
| 16   | Frontend design                         | Not started |
| 17   | API integration                         | Not started |
| 18   | Integration testing                     | Not started |
| 19   | Documentation                           | Not started |
| 20   | Viva preparation                        | Not started |

These are development milestones, not necessarily 20 separate days. Some steps will take longer than others, and frontend work will overlap with backend development.

---

# Now, specifically: What should you do in `main.cpp`?

This is where I want you to be disciplined.

Do not try to put the entire application into `main.cpp`.

Its responsibilities should evolve gradually.

| Development stage          | Responsibility of `main.cpp`                                       |
| -------------------------- | ------------------------------------------------------------------ |
| Initial setup              | Start the program and display startup information                  |
| Menu implementation        | Start the menu loop and process navigation                         |
| Class development          | Create or invoke the appropriate application components            |
| Customer management        | Route customer-related choices to the relevant module              |
| Business and visit modules | Coordinate the application flow                                    |
| Loyalty and campaigns      | Invoke the relevant services                                       |
| File handling              | Ensure loading and saving happen at appropriate points             |
| Analytics                  | Open the reporting module                                          |
| API integration            | Start the backend application and its required components          |
| Final application          | Initialize the application and hand control to its main controller |

Notice the progression: **`main.cpp` becomes a coordinator, not a giant collection of business functions.**

As the project grows, we'll move navigation into a dedicated application controller or menu component. Once we introduce the HTTP backend, the application entry point may initialize the server instead of running the console menu.

We will make that transition deliberately rather than forcing all these responsibilities into one function.

## Your immediate task: Complete Steps 1 and 2

For now, do only these things:

**Step 1**

* Create the project folders.
* Verify your C++ compiler.
* Create the initial `main.cpp`.
* Confirm that the program runs.
* Initialize Git.

**Step 2**

* Design the menu options on paper.
* Decide what happens when a user selects each option.
* Define how the application returns to the main menu.
* Define what happens when the user exits.

Do not begin customer management yet.

Once these two milestones are complete, we will move to **Step 3: designing the classes and UML diagram before implementing them**.

That is how we'll keep LocalSocial organized, understandable, and maintainable from the beginning.
