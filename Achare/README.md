The goal of this project is to design a simple login/registration system with the capability to restrict suspicious requests.

Project Summary:
In the intended system, the aim is to implement a process similar to the current login/registration flow:

1. The user first enters their mobile number.
2. If the user has registered before, they authenticate by entering a password.
3. Otherwise, a one-time 6-digit code is generated for the user, which will be sent to them via SMS.
4. The user enters the code, completes the registration, and provides personal information such as name, surname, and email.

In the login process, if the user enters the wrong password three times or if there are three incorrect combinations of username and password from a single IP, the user is blocked for 1 hour.

Similarly, in the registration process, if there are three SMS requests from a single IP but the entered code is incorrect, or if a number enters the wrong code three times, they are blocked for 1 hour.

The process is schematically illustrated in the image on the next page.

Technologies Used:
For this project, please use the Python language and the Django framework. Two suggested approaches are:

1. Have a frontend directly connected to backend models, handling registration and login operations entirely in this system.
2. Implement the system based on a RESTful API, eliminating the need for a frontend. In this case, please provide the corresponding Postman Collection.

No need to implement the section related to sending actual SMS messages.