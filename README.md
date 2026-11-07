Problem 1: Online Reservation and Booking System
1.1 Problem Statement
The administrator offers reservation services such as resorts, vehicles and conference
halls. The administrator implements check-in/check-out facilities and records customer
details. Customers manage bookings easily, the pricing is adopted, and online payment
and reservation customization are supported.
1.2 Actors
• Administrator: manages services, prices, check-in/check-out.
• Customer: searches, books, pays, modifies or cancels bookings.
• Payment Gateway: external system that processes online payments.
1.3 Functional Requirements
1. Administrator can add, edit and delete reservation services (resort, vehicle,
conference hall).
2. Administrator can set pricing (per day, per hour, seasonal rates, discounts).
3. Customer can register, log in and maintain a profile.
4. Customer can search services by type, date and price and check availability.
5. Customer can book a service and customize it (extra bed, driver, catering,
decoration).
6. System calculates the total cost according to the pricing rules.
7. Customer can pay online and receive a confirmation and invoice.
8. Administrator performs check-in and check-out and the system updates availability.
9. Customer can modify or cancel a booking, subject to the cancellation policy.
10. Administrator can view customer records and booking reports.
1.4 Non-Functional Requirements
• Secure payment (HTTPS, no card data stored).
• Prevent double booking of the same slot (transaction locking).
• Response time under 3 seconds for searches.
• Usable on desktop and mobile browsers.
1.5 Use Cases
ID Use Case Actor Description
UC1 Manage Services Admin Add, update or remove services
and prices
UC2 Search and Check
Availability
Customer Find available services for dates
UC3 Make Booking Customer Select service, customize, confirm
UC4 Pay Online Customer, Gateway Pay and get a receipt
UC5 Check-in / Check-out Admin Record arrival and departure
UC6 Modify / Cancel
Booking
Customer Change dates or cancel
UC7 View Reports Admin Booking and revenue reports
1.6 Main Classes
• User (userId, name, email, phone, role)
• Customer extends User; Administrator extends User
• Service (serviceId, type, name, description, basePrice, status)
• Pricing (pricingId, serviceId, ratePerUnit, seasonalRate, discount)
• Booking (bookingId, customerId, serviceId, startDate, endDate, customization,
totalCost, status)
• Payment (paymentId, bookingId, amount, method, status, date)
• CheckInOut (id, bookingId, checkInTime, checkOutTime)
1.7 Database Tables
users, services, pricing, bookings, payments, check_logs. A booking references one
customer and one service; a payment references one booking.
1.8 Workflow
Customer logs in, searches, selects a service and dates, customizes, the system
calculates the price, the customer pays, the booking is confirmed, the administrator
checks in the customer on arrival and checks out on departure, and the slot becomes
available again.
