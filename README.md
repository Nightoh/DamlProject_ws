# ⚡ DaX Platform ⚡

**DaX** is a platform that uses drones to deliver store orders directly to customers quickly and efficiently.

<img src="https://github.com/Nightoh/DroneDeliveryApp/assets/24417041/83e2f27a-5332-4dce-b1c5-e68af6746a6c" alt="DaX icon" width="200"/>


### I. Overview 
This project was created using the empty-skeleton template and exemplifies the proposal-accept design pattern. The workflow involves multiple parties (Stores, customers and drones), each with distinct roles and responsibilities, to manage an order from creation to delivery.

### II. Workflow

**1. Order Creation:**

  The customer initiates the process by creating an Order contract.

**2. Order Acceptance:**

  The store, as a controller, can exercise the AcceptOrder choice to prepare the order for receiving delivery proposals. At this point, the order is marked as "accepted".

**3. Delivery Proposals:**

  The drone, acting as a controller, can propose a delivery by exercising the ProposeDelivery choice on the order contract. This involves specifying the delivery fee and the proposing drone.

**4. Proposal Decision:**

  The store then has the option to either accept or reject the delivery proposal. This is done by exercising the AcceptProposal or RejectProposal choice.
If the proposal is accepted, the state of the order is updated to "pickupReady", and the delivery process can proceed (the Delivery contract is updated with the state "approved").

**5. Order Pickup:**

  Once the delivery is approved, the store and the drone collaboratively exercise the Pickup choice. This step confirms that the drone has picked up the order from the store, updating the order state to "inDelivery" and the delivery state to "inProgress".

**6. Order Delivery:**

  The drone completes the delivery by performing a handshake with the customer, which involves the customer providing a delivery pin to confirm receipt. This is done by exercising the Handshake choice.
  When completed with success the state of the delivery is updated to "completed"

**7. Order Completion:**

  Finally, the store can complete the order by exercising the CompleteOrder choice, which marks the order as "completed".
  This choice can only be exercised if the delivery status is marked as "completed".

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
