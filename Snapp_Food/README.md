### Snap Food - Software Eng (Back-end)

#### Task

System Assumptions:

● Consider a retail system that includes a number of stores (Vendors) and support personnel (Agents).

● Each store (Vendor) has a one-to-many relationship with the orders (Order) placed by users.

● Several orders are registered and stored in the Order table. The "preparation and delivery time" is maintained in the time_delivery field. For example, if an order is placed on October 23, 2021, at 14:20:00, with a time_delivery of 50 minutes, it is expected to be delivered by 15:10:00 on October 23, 2021.

● To deliver an order to the customer, a delivery person goes to the store, collects the order from the vendor, and delivers it to the customer. Different statuses of this delivery person, from the moment they are assigned to an order until its delivery, are stored in a table named Trip. The trip status can be one of the values: DELIVERED, PICKED, VENDOR_AT, ASSIGNED. Note that no order will have more than one trip.


Test Scenario:

After the "preparation and delivery time" has elapsed, the user can report a delay in the order through a web service (DelayReport Entity). It should be noted that each order can have multiple DelayReports. Subsequently, the order will undergo a process of delay investigation and tracking.

System Requirements:

To implement the operations of the system, three APIs are required:

1. Order Delay Notification API: This API is responsible for receiving and processing delay notifications for orders from users.

2. Request for Assignment API: This API handles the request to assign an order to an employee for investigation. It involves the process of allocating an order to an agent for further examination.

3. Receive Store Delay Reports API: This API is designed to retrieve reports of delays from the stores. It facilitates the system in collecting information about delays from the vendors.

Order Delay Notification

In the case of an order delay (Delay Notification API), there are two approaches:

1. If a row for the specified order has been created in the trips table, and the trip is in one of the states: ASSIGNED, VENODR_AT, or PICKED, use the following web service to receive a new estimate for the delivery time of the order. Provide an appropriate response to the client.
2. If a row for the specified order has not been created in the trips table, or if the trip is in a state other than VENDOR_AT, ASSIGNED, or PICKED, place the order in the delay queue.

The result of both approaches is stored in the "reports_delay" table.

A request is made to assign the order to an employee for inspection.

- Orders in the delay queue are assigned to the employee using the FIFO method through an API request.
Validation:

    Throughout the system's operation, conditions should never occur where:
        An order is marked as delayed before the time_delivery has elapsed.
        An order that has previously been added to the delay queue and has not been inspected yet should be added to the queue again.
        An order that has been assigned to an employee through the queue should not be reassigned to another employee until it is inspected.
        An employee with at least one delay under inspection should not be assigned another order until the inspection is complete.

Technical Considerations:

1. There is no need for employee authentication for various operations.
2. While error-free functionality is important, the efficiency of system processes in terms of speed and code quality is equally crucial. Therefore, adherence to best practices and the use of appropriate patterns are considered when reviewing this test.
3. There are no constraints on the choice of a framework.
4. Use relational databases for implementation.
5. No user interface is required for different operations, and operations should be performed through APIs.
