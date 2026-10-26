# Odoo Sales Lifecycle

In this document, we will define the lifecycle of a sale in Odoo, from the creation of a quotation up to payment reception.

## Entities
Objects created along the sales order lifecycle:

1. Quotation
2. Sales Order
3. Sale Item
4. Invoice
5. Payment
6. Delivery
7. Customer
8. Delivery

## Behaviours
State changes for the same objects, or behaviours that fire the creation of new objects:

### Quotation Creation
Creating a quote is the first step of the sales process. Following customer contact, we register their desired items to send them a quotation and receive their validation that we would like to proceed with the sale:
1. Go to the Odoo instance homepage and select Sales: 
![](images/homepage-sales.png)
1. Once on the Sales page, click on "New" at the Quotation section to create a new quotation: 
![](images/new-quotation.png)
1. On the New Quotation page, fill in the necessary information, such as customer and products: 
![](images/quotation-empty.png)
1. To define the customer's preferred delivery method, click on "Other Info" and in the Incoterm field, select from the list:
![](images/Quotation_other_info.png)
![](images/Incoterms_List.png)
1. Once the quotation has all the necessary information, click on the "Save manually" button. Alternatively, you can click the "Preview" button, which will also save the quote and then display a preview of the quote as seen by the customer on their end of Odoo: 
![](images/save-quotation.png)
![](images/sales-order-list.png)

### Quotation Confirmation / Sales order creation
Once the user has decided they want to go along with business given a specific quote, you can confirm it, which turns it into a Sales Order:
1. Once with your quote created, go to the Sales page to select said quote: ![](images/quote-list-to-confirm.png)
1. Once on the quote page, click the "Confirm" button: 
![](images/quote-confirm-button.png)
1. Confirm that the quotation has successfully turned into a Sales Order: ![](images/quotation-to-sales-order.png)

### Sales Item Reservation
#### Validating Items / Shipping
After creating the sales order, we have to validate that we can ship the products the client ordered. To do this, follow these steps:

1. Click on the "Inventory" option at Odoo's homepage:
![](images/home-inventory.png)
1. Click on the button "# To Deliver" to check your order's shipping info
![](images/orders-to-deliver.png)
1. Click on the order you want to check:
![](images/delivery-order.png)
1. In the inventory validation, click on the "Validate" button to register the transfer:
![](images/inventory-validation.png)
1. Validate that the transfer was registered as valid:
![](images/validate-validation.png)

### Invoicing
After the Sales Order has been created and the products have been validated as available in the inventory, we can proceed with invoicing:
1. Go to the Sales page for your Sales Order, and select the "Orders" option from the menu:
![](images/view-orders.png)
1. Select your desired order:
![](images/select-order.png)
1. Once in your Order page, click "Validate":
![](images/create-invoice.png) 
1. In the popup modal that follows, hit create modal:
![](images/create-invoice-modal.png)
1. In the Draft Order page that opens, click on "Confirm":
![](images/create-invoice-confirm.png)
1. The new invoice is ready to be managed:
![](images/created-invoice.png)

### Registering payments

#### Complete payment
Once the invoice has been created and sent, the business waits until the customer pays. Once he/she pays, we can register the payment as follow:
1. Go to the Accounting Dashboard
![](images/accounting-dashboard.png)
1. Click on either "Bank" or "Cash", depending on how the user paid his/her invoice
![](images/accounting-bank-cash.png)
1. Click on "New" to create an entry, and when creating the entry, place the customer, the amount paid, and in the "Memo" field, place the invoice reference. Odoo will use these informations to automatically match the credit entry created with the invoice
![](images/registering-accounting-entry.png)
1. Check that the accounts and entries match with the desired values, and if they do, click on "Validate". This will link the received payment with the invoice.
![](images/validate-accounting-entry.png)
1. Validate that the invoice status has been updated accordingly
![](images/validate-accounting-entry.png)  
![](images/invoice-paid.png)

#### Partial payments
Sometimes, the user pays on mutiple installments, depending on the accords reached with the business. Partial payments are supported on Odoo, and the process is very similar as with "Complete payments", with a few differences:
1. When a customer makes an initial payment that does not cover the total amount of the debt, the payment will still be registered, while the invoice status will be updated to "Partial" instead of "Paid".
![](images/registering-partial-payment.png)
![](images/invoice-partially-paid.png)
1. Only when all the debt has been consolidated, will the invoice change to "Paid"
![](images/partial-last-payment.png)
![](images/invoice-completely-paid.png)
