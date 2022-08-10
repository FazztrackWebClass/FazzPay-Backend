<h1 align="center">FazzPay Backend</h1>

## Contents

- [Link](#link)

- [How It Works](#how-it-works)

- [What To Do](#what-to-do)

- [Remote Database](#remote-database)

- [Endpoint](#endpoint)

## Link

- Link Heroku : https://fazzpay.herokuapp.com
- Link Cloudinary : https://res.cloudinary.com/dd1uwz8eu/image/upload/v1653276449/Fazzpay/tvcdjvikzad9caesnjmy.png
- Link Export Transaction : https://fazzpay.herokuapp.com/generate/test.pdf

## How It Works ?

1. Download Postman Collection [[here](https://drive.google.com/file/d/1tTixEuPCmnHMd2sm_8YSEqyQj9XkE8uu/view?usp=sharing)]
2. Open Your Postman App
3. Import Postman Collection
4. Create Environtments in Postman & Set :

```bash
VARIABLE : fazzpay
INITIAL VALUE : https://fazzpay.herokuapp.com
CURRENT VALUE : https://fazzpay.herokuapp.com
```

5. Test Request

## What To Do ?

1. Register using your real information
2. Open your registered email address
3. Open email and follow the instruction to verify your FazzPay account
4. Login and use the API

## Remote Database

```bash
Hostname = ec2-44-202-197-206.compute-1.amazonaws.com
Port = 3306
Username = fw6trainer
Password = Mshgj91!
```

note: don't drop or remove table and database

## EndPoint

### Module Auth

**Used for authentication**

| No. | Method | Endpoint              | Information                      |
| --- | ------ | --------------------- | -------------------------------- |
| 1.  | POST   | /auth/register        | Used for register new user.      |
| 2.  |        | /auth/login           | Used for login into app.         |
| 3.  |        | /auth/forgot-password | Used for forgot password.        |
| 4.  |        | /auth/logout          | Used for logout from system.     |
| 5.  | GET    | /auth/verify/:key     | Used for activating new account. |
| 6.  | PATCH  | /auth/reset-password  | Used for reseting password.      |

### Module User

**Used for any user feature**

| No. | Method | Endpoint                         | Information                                                                              |
| --- | ------ | -------------------------------- | ---------------------------------------------------------------------------------------- |
| 1.  | GET    | /user?page=&limit=&search=&sort= | Used for get all data user for showing in transfer page.                                 |
| 2.  |        | /user/:userId                    | Used for get user by id                                                                  |
| 3.  |        | /user/pin?pin=                   | Used for check pin true or false, work before update pin or checking pin before transfer |
| 4.  | PATCH  | /user/password/:userId           | Used to change password for user.                                                        |
| 5.  |        | /user/profile/:userId            | Used to change any info for example name and phone number.                               |
| 6.  |        | /user/image/:userId              | Used to change profile picture for user.                                                 |
| 7.  |        | /user/pin/:userId                | Used to change pin for user.                                                             |
| 8.  | DEL    | /user/image/:userId              | Used to delete profile picture for user.                                                 |

### Module Topup

**Used for topup any balance to user**

| No. | Method. | Endpoint                           | Information                    |
| --- | ------- | ---------------------------------- | ------------------------------ |
| 1.  | POST    | /transaction/topup                 | Used for topup for add balance |
| 2.  |         | /transaction/midtrans-notification | Used for midtrans notification |

### Module Transfer

**Used to all about tranfer feature needed**

| No. | Method | Endpoint              | Information                 |
| --- | ------ | --------------------- | --------------------------- |
| 1.  | POST   | /transaction/transfer | Used to create new tranfer. |

### Module Dashboard

**Used for supplying data dashboard**

| No. | Method | Endpoint           | Information                                                                           |
| --- | ------ | ------------------ | ------------------------------------------------------------------------------------- |
| 1.  | GET    | /dashboard/:userId | Used for get information totalIncome, totalExpense, data for chart Income and Expense |

### Module History

**Used for supplying data history income, expense, and topup user**

| No. | Method | Endpoint                                  | Information                                         |
| --- | ------ | ----------------------------------------- | --------------------------------------------------- |
| 1.  | GET    | /transaction/history?page=&limit=&filter= | Used for get information history transfer and topup |

### Module Export

**Used for export pdf transfer/transaction**

| No. | Method | Endpoint                           | Information                              |
| --- | ------ | ---------------------------------- | ---------------------------------------- |
| 1.  | GET    | /export/transaction/:transactionId | Used for export pdf evidence of transfer |
