step 1 completed..
a. folder structed 
b. git init
c. verified gcc/g++

Step 2. Design the main application flow

**Objective:** Decide how users will navigate LocalSocial.

Before implementing features, we need to define the application's control flow.

The first version will follow this sequence:
1. local social named big screen
with signup or login box button and a button asking about us, below this an testimonials section and below this how this works section.

2. Authenticate the user.
 Display the main dashboard or menu.
 Let the user select a module.
 Perform the requested operation.
 Return to the dashboard.
 Save changes when appropriate.
 Exit safely.


 Design the class architecture

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