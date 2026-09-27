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
Once an invoice has been created, it can be payed by following these steps:
1. Go to the Sales Order page, and click on "Invoices":
![](images/sales-invoices.png)
1. Click on send so the user can receive the invoice:
![](images/send-invoice.png)
1. Select the desired invoice delivery option, and click send:
![](images/invoice-delivery-options.png)
1. Once you have collected the payment from the customer, click on the "Pay" button.
![](images/pay-invoice.png)
1. On the following popup, validate the payment options and click on "Create Payment":
![](images/create-payment.png)
1. If the payment type was "Bank", you can confirm receiving the payment by clicking on "Payments", and then "Validate":
![](images/invoice-payments.png)
![](images/validate-payments.png)

### Linking payments and invoices
Once the payment has been validated, in the case of "Bank" payments, a corresponding bank statement must be registered to confirm the payment was real. This statement then must be reconciliated with your sales order's payment, in order to close the pending action items for the order. To do this, follow these steps:
1. Click on the accounting option on Odoo's homepage:
![](images/accounting.png)
1. Click on the Transactions option:
![](images/accounting-transactions.png)
1. Create a new transaction, with a name to identify it later:
![](images/new-transaction.png)
1. Click on the newly created transaction entry:
![](images/transaction-item.png)
1. Click on "Reset" to be able to modify the entry, configure the values for the reconciliation, and the click on "Post":
![](images/configure-transaction-entry.png)