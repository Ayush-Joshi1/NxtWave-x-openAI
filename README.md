# n8n E-commerce Order Automation System

An intelligent, fully automated e-commerce order processing workflow built with n8n that handles customer orders via Gmail, validates inventory in Google Sheets, and sends AI-powered automated responses.

## 🌟 Features

### Main Workflow - Order Processing
- **AI-Powered Email Parsing**: Uses OpenAI GPT-4.1 to extract order details from customer emails
- **Inventory Validation**: Automatically checks product availability and stock levels in Google Sheets
- **Smart Order Processing**: 
  - Accepts orders when products are in stock
  - Rejects orders for out-of-stock items
  - Updates inventory automatically after order confirmation
- **Automated Email Responses**: 
  - Sends order confirmation emails with details
  - Sends out-of-stock notifications
  - Professional email formatting

### Quotation Workflow
- **Product Inquiry Handling**: Processes quotation requests via Gmail
- **AI Information Extraction**: Extracts customer name, product name, and quantity from emails
- **Automatic Price Calculation**: Retrieves pricing from Google Sheets and calculates totals
- **Professional Quotations**: Sends formatted quotation emails with pricing and availability

### Customer Management
- **Order Tracking**: Logs all orders (accepted and rejected) in Google Sheets
- **Customer Database**: Maintains customer information including:
  - Product details
  - Shipping addresses
  - Special instructions
  - Order status

## 🛠️ Technology Stack

- **n8n**: Workflow automation platform
- **OpenAI GPT-4.1-mini**: AI-powered text extraction and parsing
- **Gmail API**: Email trigger and sending
- **Google Sheets API**: Inventory and customer data management

## 📋 Prerequisites

- n8n instance (self-hosted or cloud)
- OpenAI API key
- Google Cloud Project with Gmail and Sheets APIs enabled
- OAuth2 credentials for Gmail and Google Sheets

## 🚀 Setup Instructions

1. **Import Workflow**
   - Import `Final.json` into your n8n instance

2. **Configure Credentials**
   - Add OpenAI API credentials
   - Set up Gmail OAuth2 authentication
   - Configure Google Sheets OAuth2 authentication

3. **Set Up Google Sheets**
   - Create two Google Sheets:
     - **Stock Sheet**: Columns - ProductID, ProductName, QuantityInStock, Price
     - **Customers Sheet**: Columns - Name, Email, Product Name, Product ID, Quantity, Shipping Address, Special Instruction, ORDER STATUS

4. **Configure Gmail Labels**
   - Create Gmail label: `Sales_Order` for order processing
   - Create Gmail label for quotation requests (as configured)

5. **Update Sheet IDs**
   - Replace the Google Sheet IDs in the workflow with your own sheet IDs

6. **Activate Workflow**
   - Enable both workflows in n8n

## 📧 Email Format

### For Orders
Customers should include:
- Product name
- Quantity
- Customer name
- Shipping address
- Special instructions (optional)

### For Quotations
Customers should include:
- Product name
- Quantity
- Customer name
- Contact email

## 🔄 Workflow Logic

### Order Processing Flow
1. Gmail trigger detects emails with `Sales_Order` label
2. Extract sender email address
3. AI parses email content to extract order details
4. Query Google Sheets for product information
5. Check if product name matches and quantity is available
6. **If available**:
   - Update inventory (reduce stock)
   - Log order in customer sheet
   - Send confirmation email
7. **If not available**:
   - Log rejection in customer sheet
   - Send out-of-stock notification

### Quotation Flow
1. Gmail trigger detects quotation request emails
2. AI extracts product name, quantity, and customer details
3. Query stock sheet for product and pricing
4. **If product found**:
   - Calculate total price
   - Send detailed quotation email
5. **If not found**:
   - Send clarification request email

## 📊 Data Structure

### Stock Sheet
```
ProductID | ProductName | QuantityInStock | Price
```

### Customer Orders Sheet
```
Name | Email | Product Name | Product ID | Quantity | Shipping Address | Special Instruction | ORDER STATUS
```

## 🎯 Use Cases

- Small to medium e-commerce businesses
- Inventory management automation
- Customer service automation
- Order processing optimization
- Quotation generation

## 🔒 Security Notes

- API credentials are stored securely in n8n credential system
- Email addresses are extracted dynamically from incoming emails
- No hardcoded sensitive information in the workflow

## 🤝 Contributing

Feel free to fork this repository and customize the workflow for your needs!

## 📄 License

This workflow is provided as-is for educational and commercial use.

## 👤 Author

Created with ❤️ using n8n workflow automation

---

**Note**: Make sure to update all credential IDs and Google Sheet IDs before using this workflow in your n8n instance.
