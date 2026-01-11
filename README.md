# n8n E-commerce Order Automation System

An intelligent, fully automated e-commerce order processing system built using n8n that processes customer orders via Gmail, validates inventory in Google Sheets, and sends AI-powered automated responses.

## 🌐 Deployment Status (IMPORTANT)

### Project Deployment

This project is deployed and running on n8n Cloud (14-day trial) as an internal automation system.

**Trigger Type**: Gmail Trigger (Label-based)

**Execution Mode**: Event-driven (email-based)

**Public Webhook**: Not applicable (no external HTTP trigger used)

📌 Since this is a backend automation workflow, it does not expose a public URL like a website.  
Execution is automatically triggered by incoming emails in Gmail.

## 🎥 Live Demo (Deployed Execution Proof)

👉 **Demo Video**: https://youtu.be/3ByHprWNwbY  

The demo shows:

Live workflow execution on n8n Cloud  

Email trigger activation  

Inventory update in Google Sheets  

Automated email responses  

This demo serves as the Project Published (Deployed) Link.

## 🌟 Features

### Main Workflow – Order Processing

AI-Powered Email Parsing: Uses OpenAI GPT-4.1-mini to extract order details from customer emails  

Inventory Validation: Checks product availability in Google Sheets  

Smart Order Handling:

Accepts orders when stock is available  

Rejects orders when stock is unavailable  

Automatically updates inventory  

Automated Email Responses:

Order confirmation emails  

Out-of-stock notifications  

Professionally formatted replies  

### Quotation Workflow

Product inquiry handling via Gmail  

AI-based extraction of product and customer details  

Automatic price calculation from Google Sheets  

Professional quotation emails  

### Customer Management

Logs all orders (accepted/rejected) in Google Sheets  

Maintains customer data including order status and instructions  

## 🛠️ Technology Stack

n8n Cloud  

OpenAI GPT-4.1-mini  

Gmail API  

Google Sheets API  

## 🚀 Setup Instructions

Import Final.json into your n8n instance  

Configure credentials:

OpenAI API  

Gmail OAuth2  

Google Sheets OAuth2  

Create Google Sheets:

Stock Sheet  

Customer Orders Sheet  

Configure Gmail labels:

Sales_Order  

Quotation_Request  

Update Google Sheet IDs in the workflow  

Activate both workflows  

## 🔄 Workflow Logic

### Order Processing Flow

Gmail trigger detects emails with Sales_Order label  

AI extracts order details  

Inventory is checked in Google Sheets  

If in stock:

Inventory updated  

Order logged  

Confirmation email sent  

If out of stock:

Order marked rejected  

Notification email sent  

### Quotation Flow

Gmail trigger detects quotation requests  

AI extracts product & quantity  

Price calculated from stock sheet  

Quotation email sent automatically  

## 📊 Data Structure

### Stock Sheet

ProductID | ProductName | QuantityInStock | Price  

### Customer Orders Sheet

Name | Email | Product Name | Product ID | Quantity | Shipping Address | Special Instruction | ORDER STATUS  

## 🎯 Use Cases

E-commerce order automation  

Inventory management  

Customer support automation  

Quotation generation systems  

## 🔒 Security Notes

Credentials stored securely in n8n  

No sensitive data hardcoded  

Dynamic email extraction  

## 📄 License

Provided for educational and commercial use.

## 👤 Author

Created with ❤️ using n8n workflow automation
