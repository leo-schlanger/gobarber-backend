<div align="center">
  <img width="300" src="./assets/logo.png" />

  # In development...
</div>
---

# 📓  Description

---

# 📐  Architecture

- [SOLID](https://en.wikipedia.org/wiki/SOLID)
- [DDD  (Domain-Driven Design)](https://en.wikipedia.org/wiki/Domain-driven_design)
- [TDD (Test Driven Development)](http://agiledata.org/essays/tdd.html)

---

# 🚀 Technologies

- [node.js](https://nodejs.org/en/docs/)
- [express](https://expressjs.com/pt-br/api.html)
- [typeORM](https://typeorm.io/#/)
- [postgreSQL](https://www.postgresql.org/)
- [MongoDB](https://www.mongodb.com/)
- [Socket.io](https://socket.io/)
- [tsyringe](https://github.com/microsoft/tsyringe)
- [nodemailer](https://nodemailer.com/about/)
- [ethereal](https://ethereal.email/)
- [jest](https://jestjs.io/docs/en/getting-started)

---
# 📦 System Features Mapping

## Password Recovery

**functional requirements**

 - The user should be able to recover your password using your email;
 - The user should receive an email with password recovery instructions;
 - The user should be able to reset his password;

**non-functional requirements**

  - Use mailtrap to test shipments in a dev environment;
  - Use amazon ses for production shipments;
  - Sending email should take place in the background (background job);

**business rules**

  - The link sent by email to reset the password, must expire in 2 hours;
  - The user needs to confirm a new password before resetting his password;

## Profile Update

**functional requirements**

- The user should be able update your name, email and password;

**business rules**

  - The user cannot change his email to an email already used;
  - To update your password, the user must enter the old password;
  - To update your password, the user needs to confirm the new password;

## Provider Dashboard

**functional requirements**

 - The user should be able to list their appointments for a specific day;
 - The provider must receive a notification whenever there is a new appointment;
 - The provider should be able to view unread notifications;

**non-functional requirements**

  - Provider appointments on the day must be cached;
  - Service provider notifications must be stored in MongoDB;
  - Service provider notifications must be sent in real time using Socket.io;


**business rules**

  - The notification must have a read or unread status so that the provider can control;

## Appointments Services

**functional requirements**

 - The user should be able to list all registered service providers;
 - The user should be able to list the days of a month with at least one available time from a provider;
 - The user should be able to list the hours available on a specific day of a provider;
 - The user should be able to make a new appointment with a provider;

**non-functional requirements**

  - The list of service providers must be cached;

**business rules**

  - Each appointment must last 1 hour;
  - Appointments must be available between 8am to 6pm (first at 8am, last at 5pm);
  - The user cannot schedule at an already busy appointment;
  - The user cannot schedule an appointment that has already passed;
  - The user cannot schedule services with himself;
