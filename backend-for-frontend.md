# Backend for Frontend

[microsoft-learn](https://learn.microsoft.com/en-us/azure/architecture/patterns/backends-for-frontends)

- Very often, different frontends have to utilize the same backends. Over time, conflicting requirements from the different frontends (web app, mobile app) make the backend inefficient

- The solution is to create another layer between the frontend and the backend, that handles the device or frontend specific formatting and processing of data from the backend

- This pattern causes code duplication