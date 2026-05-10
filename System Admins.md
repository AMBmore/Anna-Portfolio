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

# Step 2 of 2: How to process a Purchase Order in the Open Orders File

• To complete AFTER the signature  
• Do not process order on the day of a home game, as it effects game night profit margins.  

---

## 📄 PDF:
19) Download the signed PO from email and save to the “Open Orders” file (add “signed” to save as.)  
20) Delete the old, unsigned PDF.  

---

## 🔵 POS:
21) Press “Quote recall”  
22) Flip through to find the correct ticket. Then select “Recall Quote.”  If you recall the wrong one, press Quote > reassign the date. Close.  
23) Select “Go to Payments”  
24) Select “Other payments”  
25) Select “On Account”  
26) Select “Ok”, and make sure the price matches  
27) Input the Account Number from the PDF, even if it was an “Official & Proud Partner”.  
28) Select “yes” for ticket complete  
29) Don’t close the ticket number that comes up.  

---

## 📄 PDF:
30) When provided with the ticket number (TINT1 etc.), change the text color to black, and write the ticket number under “Bill Number” on the PDF.  
• To copy and paste the same font: right click on the PDF and select “Open in Microsoft Edge,” OR use a snipping tool.  

31) Press Save, not Save as.  
32) Rename the PDF file: Replace the date with the Billing Number.  

33) Once all POs have been processed for the day, email the Finance department with the PDFs for all completed POs. Subject line: “Completed POs + DD/MM/YYYY”  

34) Move the PDFs from “Open Orders” file to the “Completed” file, in the folders for the correct month and year when the order was processed.  

35) Shred the original purchase order paper copies once the digital files have been emailed to Finance and moved to the completed folder.  

---

# How to Process Internal Gift Card Purchase Orders:

*Note: There are no discounts or taxes for Gift Cards*  

## 🟢 Excel:
1) Input total price in the top of the price column  
2) Leave DISCOUNT blank  
3) Manually change the GST & PST tax boxes to $0.00  
4) Change the name of the file (see step 12) and Save two copies to Excel and PDF  
5) Send the PO to be signed BEFORE putting into the POS system  
6) Once Signed, save the signed PDF to the Open Orders file, and delete the old PDF  

---

## 🔵 POS (Once Signed): 
7) Press “Sell GC” button on the Right hand side  
8) In “Description”, type “Gift Card”  
9) Type in the number on the card, or scan with a barcode scanner for better accuracy. Doublecheck the number after scanning.  
10) Input the requested funds amount  
11) Press “OK”  
12) Insert the Gift Card into a Gift Card holder and write the amount on the back.  

13) Select “Customer Look up”, and look up the Account Number, not the customer name. If the number doesn’t come up, use a similar one.  
14) Select “Go to Payments”  
15) Select “Other Payments”  
16) Select “On Account”  
17) Select OK  
18) Input the Account Number – Note: Use the exact one written on the PDF, even if you used a diff. one in the customer lookup.  
19) Select “yes” for complete  
20) Don’t close the ticket number that comes up.  

---

## 📄 PDF:
21) Right click on the PDF and select “Open in Microsoft Edge,”  
22) Using the text tool, change the Billing Number to the one provided by the POS.  
a. E.g. “TINT1.” Save the text color to black.  

23) Select “Save”, not “Save as,” within Edge or Chrome.  
24) Rename the PDF file: Replace the date with the Billing Number.  
25) Email the Finance department as specified above in Step 33  
26) Remember to put taxes back to GST = 0.05 and PST = 0.07 in the Excel Template once finished  
27) Delete the old Excel file.  

---

## 🔵 How to Close NCR Counterpoint:

This task is normally completed at the end of the day after processing Purchase Orders  

1) Exit out of the POS but remain in the small window  
2) Select “Point of Sale”  
3) Select “Drawers”  
4) Select “Drawer Management”  
5) Make sure it says “01INT”  
6) Select the account that says “Active”  
7) Select “Reconcile”  
8) Select “yes”  
9) Enter all of the data from the “Amount Expected” column into the adjacent “Amount Reconciled” column next to it.  
10) Make sure the “Total/Over” column = $0.00  
11) Select “Ok” for Drawer Closed  
12) Once the order says “Reconciled”, select “post”  
13) Check the box that says “Use Ticket Date”, and leave the date empty.  
14) Select “Post”  
15) Do not print the Z tape  
16) Select “Ok”  
17) Email the Finance department as specified above in Step 33  


