
# SQL with GPT-2

SQL with GPT-2 is a model developed to take prompts for databases and provide you with the SQL code generator as a result.



The model was created via training GPT-2 117M model on a dataset of 90,000 tokens (Not reached yet). 

# Instructions

* Clone OpenAI's GPT-2 Repository (https://github.com/openai/gpt-2/)
* Add a folder named 'model' in the directory
* Clone SQL_with_GPT-2 into the 'model' folder
* Run in bash:
```BASH
python src/interactive_conditional_samples.py --model_name SQL_with_GPT-2
```
## Usage/Examples

Prompt:

```
I'm developing a hotel reservation system. We need to manage room bookings, guest information, room types, and payment processing. 
Each room should have details like room number, type, and rate. 
Guests can make reservations, and we want to record their stay information. 
Additionally, we need to handle room availability and generate invoices for guests upon checkout.
```

Output:

```SQL
CREATE TABLE Rooms (RoomID INT PRIMARY KEY, RoomNumber INT, RoomType VARCHAR(50), Rate DECIMAL(10, 2)); 
CREATE TABLE Guests (GuestID INT PRIMARY KEY, FirstName VARCHAR(50), LastName VARCHAR(50), Email VARCHAR(100), Phone VARCHAR(20)); CREATE TABLE Reservations (ReservationID INT PRIMARY KEY, GuestID INT, RoomID INT, CheckInDate DATE, CheckOutDate DATE); 
CREATE TABLE Payments (PaymentID INT PRIMARY KEY, ReservationID INT, Amount DECIMAL(10, 2), PaymentDate DATE); 
CREATE TABLE RoomInventory (InventoryID INT PRIMARY KEY, RoomID INT, Quantity INT); 
CREATE TABLE Invoices (InvoiceID INT PRIMARY KEY, ReservationID INT, Amount DECIMAL(10, 2), InvoiceDate DATE);
```



## Current Progress

As of this moment, SQL with GPT-2 has been trained on 4000 tokens via Google Colab.

* Next goal: 10,000 tokens. 
* Expected update: 13/09/2023

