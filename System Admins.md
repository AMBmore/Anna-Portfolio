---
title: Systems Administration
layout: default
parent: Technical Writing Samples
nav_order: 2
---

# How to Process Internal Purchase Orders  

This technical manual was developed to train staff on creating and processing Internal Purchase Orders for True North Sports + Entertainment. After identifying a lack of formal documentation for this multi-step administrative workflow, I created a user-focused guide to standardize procedures and reduce onboarding time. This guide has been successfully used to onboard new office staff, reducing training time from approximately one month to one week.

## The manual includes:

- Plain-language procedural instructions
- A glossary of technical and organizational terminology
- Numbered step-by-step workflows
- Cross-referenced navigation between NCR Counterpoint and Excel templates
- Color-coded sections optimized for dual-monitor workflows
- Error-prevention guidance for common processing mistakes  

## Systems and Tools Used

- NCR Counterpoint POS System  
- Microsoft Excel  
- PDF editing software  
- Shared network drives (R Drive)  
- Windows-based administrative environment  
- Dual-monitor workflow setup  

## Skills Demonstrated

- Technical documentation and procedural writing  
- Systems administration workflow support  
- Business process standardization  
- User onboarding and training documentation  
- POS system administration (NCR Counterpoint)  
- File management and digital record organization  
- Workflow optimization and error reduction  
- Cross-system workflow coordination  
- Administrative troubleshooting  
- Data entry accuracy and quality control  
- Accessibility-focused instruction design  
- Multi-step process documentation  

## Glossary

| Term              | Definition |
|-------------------|------------|
| **PO**            | A Purchase Order (PO) is a legally binding document issued by a buyer to a seller outlining the terms of specific goods and services, including item or service descriptions, price, and quantities. |
| **POS system**    | A Point of Sale system used to process customer transactions, checkout payments, and manage inventory for a business. |
| **R Network Drive** | The private network drive created for Retail and Marketing documents. |
| **Open Order file** | The file folder in the R Network Drive for storing in-progress Internal Purchase Orders. |
| **Completed file** | The file folder in the R Network Drive for storing completed Internal Purchase Orders. |

---

## Technical Manual

# Step 1 of 2: Creating Internal Purchase Orders

*Note: Do not process orders on home game days, as this affects the accuracy of daily profit margins.*

Open both systems in a dual-monitor setup:

🔵 = POS System in NCR Counterpoint  
🟢 = Internal PO Template in Excel and PDF document format  

---

## 🔵 Activating NCR Counterpoint (POS)

1) Activate a till by selecting “Touchscreen/Cashier.”  
2) Log in using “01INT.”  
3) Select “Activate Drawer.”  
4) Input “0.00” for both cash and Shopify.  
5) Select “Ok.”  
6) Once the POS system loads, select “Cashier.”  

### 🔵 Starting a Purchase Order in the POS System

1) Select “Item Look Up” and search for the requested items.  
2) Select each item to add it to the purchase order.  

---

## 🟢 Creating the Internal Purchase Order Excel Document

2) In the R Network Drive, navigate to: “Marketing” > “Retail” > “Internal Purchase Order”  

3) Select folder “O1JGM.”  

4) Use the template file to digitize the paper Purchase Order request in Excel.  

5) Copy the following information exactly as written on the form:

- Person’s name  
- RE: Subject  
- Quantity  
- Date  
- Account Number  

*Note: In the “Goods/Services - Details” column, use the item names exactly as they appear in the POS system rather than the handwritten form. Do not use all capital letters.*

6) In the “Price” column, input only the subtotal (🔵 located in the bottom-left box within the POS system) into the first “Price” field. Leave the remaining “Price” fields blank.  

---

## 🔵 POS Processing

7) To apply the discount, select “Customer Look Up” and search using the account number rather than the name listed on the request form. If the exact account number does not appear, select the closest match.  

8) Record the department name associated with the account number on the paper PO copy. This information will be used later when renaming the file.  

9) Skip this section if the order does not include a jersey item.  

→ **If the item is a Blank Jersey:**  

- For player jerseys, select:  
  “Embroidered Cresting” > “Embroidered Adult PLAYER” or “Embroidered Adult Cresting” for other custom names.  

- For specialty jerseys or youth/infant jerseys, use the additional quick-guide buttons located on the right-hand side of the POS system.  

→ Open the Word document titled “Internal PO pricing for blank jerseys.” Select the item in the POS system and choose “Price Override.”  

- If the POS price is higher than the Word document price, retain the POS price.  
- If the POS price is lower, change it to match the Word document price.  

*Always use the higher of the two pricing values.*  

→ **Premium jerseys with names:**  
Assume the jersey is pre-made and retain the existing POS price unless embroidery is specifically requested.  

→ **If embroidering a jersey:**  
Embroidery is priced at $10 off the original jersey price. After applying the account number discount, return the jersey price to its original amount and subtract $10.  

*(Typically $89.99 after the embroidery discount.)*  

→ **Jets jerseys:**  
Select “Embroidery” or “Cresting,” then select the player name and number displayed in the system.  

→ **Moose jerseys:**  
Use the green selection boxes located in the middle-right section of the POS screen. You may need to move the POS system to a larger monitor for visibility. No player name or number will appear.  

*Additional Notes:*  

- Override the price of Jets Gear bags to “$0” if additional items are included in the order.  
- Refer to the “GL budget codes” document for special Name Bar pricing for full-time staff.  

---

10) To complete the “Discount” field in the Excel spreadsheet:

- Subtract the original Excel subtotal from the updated POS subtotal using a calculator.  

---

## 🟢 Excel Processing

11) Enter the calculated discount amount in the “DISC.” field using a minus symbol.  

- Verify that the totals and taxes match in both the POS system and the Excel spreadsheet.  
- If the Excel total differs by one cent, manually adjust it by single-clicking the “Total” field.  

12) Rename the file using the following naming convention:

`Original-Date-of-Purchase-Order_Department_Name of Person Requesting Purchase Order_optional additional information`

Example:

`Dec-20-2025_Moose Game Production_John Doe_Moose game giveaway`

13) Save the file in both Excel and PDF formats within the “Open Orders” folder.  

---

## 🔵 Saving the POS Quote

*Note: If the right-hand side of the POS screen is displaying “Embroidery,” select the “Go Back” button located in the top-left corner.*

14) Select “Quote” on the right-hand side of the POS system.  
15) Select “Expiration Date” and set the date to the end of the following month.  
16) Ignore the quote number displayed and select “Close.”  
17) Email the PDF copy of the Purchase Order to the requester and ask them to digitally sign and return it.  
18) Await the signed response before proceeding.   

---

# Step 2 of 2: Processing a Purchase Order in the Open Orders File

- Complete this process only AFTER receiving the signed Purchase Order.  
- Do not process orders on home game days, as this affects the accuracy of game-night profit margins.  

---

## 📄 PDF Processing

19) Download the signed Purchase Order from email and save it to the “Open Orders” folder. Add “signed” to the file name when saving.  
20) Delete the previous unsigned PDF copy.  

---

## 🔵 POS Processing

21) Select “Quote Recall.”  
22) Browse through the available tickets to locate the correct quote, then select “Recall Quote.”  If the incorrect quote is recalled, select “Quote” > reassign the date > “Close.”  
23) Select “Go to Payments.”  
24) Select “Other Payments.”  
25) Select “On Account.”  
26) Select “Ok” and verify that the total price matches the Purchase Order.  
27) Input the Account Number listed on the PDF, even if the account is marked as an “Official & Proud Partner.”  
28) Select “Yes” to complete the ticket.  
29) Do not close the ticket number window that appears.  

---

## 📄 Updating the PDF

30) Once the ticket number is generated (e.g., “TINT1”), change the text color to black and enter the ticket number under the “Bill Number” field on the PDF.  To match the existing font style, right-click the PDF and select “Open in Microsoft Edge,” or use a snipping tool for reference.  
31) Select “Save,” not “Save As.”  
32) Rename the PDF file by replacing the date portion with the Billing Number.  
33) After all Purchase Orders for the day have been processed, email the Finance department with all completed PDF Purchase Orders attached.
Subject line format: `Completed POs + DD/MM/YYYY`  
34) Move the completed PDFs from the “Open Orders” folder to the appropriate “Completed” folder for the correct month and year.  
35) Shred the original paper Purchase Orders once the digital copies have been emailed to Finance and moved to the completed folder.  

---

# Processing Internal Gift Card Purchase Orders

*Note: Gift Card Purchase Orders do not include discounts or taxes.*  

---

## 🟢 Excel Processing

1) Input the total price in the first “Price” field.  
2) Leave the “DISCOUNT” field blank.  
3) Manually change the GST and PST fields to `$0.00`.  
4) Rename the file according to the naming convention described in Step 12, then save both an Excel and PDF copy.  
5) Send the Purchase Order for signature approval BEFORE entering the order into the POS system.  
6) Once signed, save the signed PDF to the “Open Orders” folder and delete the previous unsigned PDF.  

---

## 🔵 POS Processing (After Signature Approval)

7) Select the “Sell GC” button on the right-hand side of the POS system.  
8) In the “Description” field, enter “Gift Card.”  
9) Enter the Gift Card number manually or scan the barcode for improved accuracy. Double-check the number after scanning.  
10) Input the requested funds amount.  
11) Select “OK.”  
12) Insert the Gift Card into a Gift Card holder and write the dollar amount on the back.  
13) Select “Customer Look Up” and search using the Account Number rather than the customer name. If the exact number is unavailable, select the closest match.  
14) Select “Go to Payments.”  
15) Select “Other Payments.”  
16) Select “On Account.”  
17) Select “OK.”  
18) Input the Account Number exactly as written on the signed PDF, even if a different account was used during the lookup process.  
19) Select “Yes” to complete the ticket.  
20) Do not close the ticket number window that appears.  

---

## 📄 Updating the Gift Card PDF

21) Right-click the PDF and select “Open in Microsoft Edge.”  
22) Using the text tool, replace the Billing Number with the ticket number provided by the POS system.  
  - Example: `TINT1`  
  - Ensure the text color is black.
      
23) Select “Save,” not “Save As,” within Microsoft Edge.  
24) Rename the PDF file by replacing the date portion with the Billing Number.  
25) Email the Finance department following the instructions provided in Step 33.  
26) Restore the GST and PST fields in the Excel template to:  
  - GST = `$0.05`  
  - PST = `$0.07`
    
27) Delete the old Excel file once processing is complete.  

---

# 🔵 Closing NCR Counterpoint

This task is typically completed at the end of the day after all Purchase Orders have been processed.  

1) Exit the POS screen while remaining within the smaller NCR Counterpoint window.  
2) Select “Point of Sale.”  
3) Select “Drawers.”  
4) Select “Drawer Management.”  
5) Verify that the account displays “01INT.”  
6) Select the account marked “Active.”  
7) Select “Reconcile.”  
8) Select “Yes.”  
9) Enter each value from the “Amount Expected” column into the adjacent “Amount Reconciled” column.  
10) Verify that the “Total/Over” field displays `$0.00`.  
11) Select “Ok” to close the drawer.  
12) Once the order status displays “Reconciled,” select “Post.”  
13) Check the box labeled “Use Ticket Date,” and leave the date field blank.  
14) Select “Post.”  
15) Do not print the Z tape.  
16) Select “Ok.”  
17) Email the Finance department according to the instructions provided in Step 33.  
