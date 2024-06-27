# ⚡ DaX Platform ⚡

**DaX** is a platform that uses drones to deliver store orders directly to customers quickly and efficiently.

<img src="https://github.com/Nightoh/DroneDeliveryApp/assets/24417041/83e2f27a-5332-4dce-b1c5-e68af6746a6c" alt="DaX icon" width="200"/>


### I. Overview 
This project was created using the empty-skeleton template and exemplifies the proposal-accept design pattern. The workflow involves multiple parties (Stores, customers and drones), each with distinct roles and responsibilities, to manage an order from creation to delivery.

### II. Workflow

**1. Order Creation:**

  Signatory: A signatory (typically a customer) initiates the process by creating an Order contract.

**2. Order Acceptance:**

  Controller: The store, as a controller, can exercise the AcceptOrder choice to prepare the order for receiving delivery proposals. At this point, the order is marked as "accepted".

**3. Delivery Proposals:**

  Controller: A drone, acting as a controller, can propose a delivery by exercising the ProposeDelivery choice on the order contract. This involves specifying the delivery fee and the proposing drone.

**4. Proposal Decision:**

  Controller: The store then has the option to either accept or reject the delivery proposal. This is done by exercising the AcceptProposal or RejectProposal choice.
If the proposal is accepted, the state of the order is updated, and the delivery process can proceed.

**5. Order Pickup:**

  Controller: Once a proposal is accepted, the store and the drone collaboratively exercise the Pickup choice. This step confirms that the drone has picked up the order from the store.

**6. Order Delivery:**

  Controller: The drone completes the delivery by performing a handshake with the customer, which involves the customer providing a delivery pin to confirm receipt. This is done by exercising the Handshake choice.

**7. Order Completion:**

  Controller: Finally, the store completes the delivery by exercising the CompleteOrder choice, marking the order as "completed".

### III. Building
To compile the project
```
$ daml build
```

### IV. Testing
To test all test scripts run:
```
$ daml test
```

### V. Running
To load the project into the sandbox and start navigator:
```
$ daml start
```
