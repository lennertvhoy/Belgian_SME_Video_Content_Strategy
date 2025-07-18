# Technical Demo Setup - E-facturatie Power Automate
## Complete Environment Configuration Guide

### 🏗️ Environment Requirements

#### **Microsoft 365 Setup**
```
Required Licenses:
- Power Automate Premium (€15/user/month)
- Dynamics 365 Sales Trial (free 30 days)
- Microsoft Teams (included)
- SharePoint Online (included)

Optional but Recommended:
- Azure subscription (free tier sufficient)
- Power BI Pro (for advanced reporting)
```

#### **Development Environment**
```
Tools Required:
- Modern browser (Chrome/Edge recommended)
- Postman (for API testing)
- Visual Studio Code (XML/JSON editing)
- Notepad++ (file editing)

Test Data:
- Sample UBL-XML files
- Fake company data (suppliers/customers)
- Demo BTW numbers
```

### 📁 Sample Files to Create

#### **1. Sample UBL Invoice (UBL-Invoice-Sample.xml)**
```xml
<?xml version="1.0" encoding="UTF-8"?>
<Invoice xmlns="urn:oasis:names:specification:ubl:schema:xsd:Invoice-2"
         xmlns:cac="urn:oasis:names:specification:ubl:schema:xsd:CommonAggregateComponents-2"
         xmlns:cbc="urn:oasis:names:specification:ubl:schema:xsd:CommonBasicComponents-2">
    <cbc:ID>INV-2024-001</cbc:ID>
    <cbc:IssueDate>2024-01-15</cbc:IssueDate>
    <cbc:DueDate>2024-02-15</cbc:DueDate>
    
    <cac:AccountingSupplierParty>
        <cac:Party>
            <cbc:EndpointID schemeID="0208">BE0123456789</cbc:EndpointID>
            <cac:PartyName>
                <cbc:Name>Demo Leverancier BV</cbc:Name>
            </cac:PartyName>
            <cac:PostalAddress>
                <cbc:StreetName>Teststraat 123</cbc:StreetName>
                <cbc:CityName>Antwerpen</cbc:CityName>
                <cbc:PostalZone>2000</cbc:PostalZone>
                <cac:Country>
                    <cbc:IdentificationCode>BE</cbc:IdentificationCode>
                </cac:Country>
            </cac:PostalAddress>
        </cac:Party>
    </cac:AccountingSupplierParty>
    
    <cac:AccountingCustomerParty>
        <cac:Party>
            <cbc:EndpointID schemeID="0208">BE0987654321</cbc:EndpointID>
            <cac:PartyName>
                <cbc:Name>Uw KMO BV</cbc:Name>
            </cac:PartyName>
        </cac:Party>
    </cac:AccountingCustomerParty>
    
    <cac:TaxTotal>
        <cbc:TaxAmount currencyID="EUR">210.00</cbc:TaxAmount>
        <cac:TaxSubtotal>
            <cbc:TaxableAmount currencyID="EUR">1000.00</cbc:TaxableAmount>
            <cbc:TaxAmount currencyID="EUR">210.00</cbc:TaxAmount>
            <cac:TaxCategory>
                <cbc:ID>S</cbc:ID>
                <cbc:Percent>21</cbc:Percent>
                <cac:TaxScheme>
                    <cbc:ID>VAT</cbc:ID>
                </cac:TaxScheme>
            </cac:TaxCategory>
        </cac:TaxSubtotal>
    </cac:TaxTotal>
    
    <cac:LegalMonetaryTotal>
        <cbc:LineExtensionAmount currencyID="EUR">1000.00</cbc:LineExtensionAmount>
        <cbc:TaxExclusiveAmount currencyID="EUR">1000.00</cbc:TaxExclusiveAmount>
        <cbc:TaxInclusiveAmount currencyID="EUR">1210.00</cbc:TaxInclusiveAmount>
        <cbc:PayableAmount currencyID="EUR">1210.00</cbc:PayableAmount>
    </cac:LegalMonetaryTotal>
    
    <cac:InvoiceLine>
        <cbc:ID>1</cbc:ID>
        <cbc:InvoicedQuantity unitCode="EA">5</cbc:InvoicedQuantity>
        <cbc:LineExtensionAmount currencyID="EUR">1000.00</cbc:LineExtensionAmount>
        <cac:Item>
            <cbc:Name>IT Consultancy Services</cbc:Name>
        </cac:Item>
        <cac:Price>
            <cbc:PriceAmount currencyID="EUR">200.00</cbc:PriceAmount>
        </cac:Price>
    </cac:InvoiceLine>
</Invoice>
```

#### **2. JSON Schema for Power Automate (UBL-Schema.json)**
```json
{
    "type": "object",
    "properties": {
        "Invoice": {
            "type": "object",
            "properties": {
                "ID": {"type": "string"},
                "IssueDate": {"type": "string"},
                "DueDate": {"type": "string"},
                "AccountingSupplierParty": {
                    "type": "object",
                    "properties": {
                        "Party": {
                            "type": "object",
                            "properties": {
                                "EndpointID": {"type": "string"},
                                "PartyName": {
                                    "type": "object",
                                    "properties": {
                                        "Name": {"type": "string"}
                                    }
                                }
                            }
                        }
                    }
                },
                "LegalMonetaryTotal": {
                    "type": "object", 
                    "properties": {
                        "PayableAmount": {"type": "string"}
                    }
                }
            }
        }
    }
}
```

### 🔧 Power Automate Flow Setup

#### **Flow 1: Inkomende Peppol Facturen**

**Step 1: Create HTTP Trigger**
```
Flow Name: "Peppol - Inkomende Factuur Verwerking"
Trigger: "When a HTTP request is received"
Method: POST
Content-Type: application/xml
```

**Step 2: Parse XML to JSON**
```
Action: "Compose"
Expression: xml(triggerBody())
Description: "Convert XML to JSON for easier processing"
```

**Step 3: Extract Invoice Data**
```
Action: "Parse JSON"
Content: outputs('Compose')
Schema: [Use UBL-Schema.json from above]
```

**Step 4: Validate Supplier**
```
Action: "Condition"
Left Value: body('Parse_JSON')?['Invoice']?['AccountingSupplierParty']?['Party']?['EndpointID']
Condition: contains
Right Value: "BE0123456789,BE0987654321,BE0555444333"
```

**Step 5a: If Supplier Valid - Create Record**
```
Action: "Create a new record" (Dynamics 365)
Table: Invoices
Fields:
- Invoice Number: body('Parse_JSON')?['Invoice']?['ID']
- Supplier: body('Parse_JSON')?['Invoice']?['AccountingSupplierParty']?['Party']?['PartyName']?['Name']
- Amount: body('Parse_JSON')?['Invoice']?['LegalMonetaryTotal']?['PayableAmount']
- Status: "Pending Approval"
```

**Step 5b: Send Teams Notification**
```
Action: "Post adaptive card in a chat or channel"
Recipient: [Your Teams channel]
Card: [Use Adaptive Card template below]
```

#### **Adaptive Card Template for Teams**
```json
{
    "type": "AdaptiveCard",
    "version": "1.3",
    "body": [
        {
            "type": "TextBlock",
            "text": "Nieuwe Peppol Factuur Ontvangen",
            "weight": "Bolder",
            "size": "Medium"
        },
        {
            "type": "FactSet",
            "facts": [
                {
                    "title": "Factuur Nr:",
                    "value": "${body('Parse_JSON')?['Invoice']?['ID']}"
                },
                {
                    "title": "Leverancier:",
                    "value": "${body('Parse_JSON')?['Invoice']?['AccountingSupplierParty']?['Party']?['PartyName']?['Name']}"
                },
                {
                    "title": "Bedrag:",
                    "value": "€${body('Parse_JSON')?['Invoice']?['LegalMonetaryTotal']?['PayableAmount']}"
                }
            ]
        }
    ],
    "actions": [
        {
            "type": "Action.Submit",
            "title": "Goedkeuren",
            "data": {"action": "approve"}
        },
        {
            "type": "Action.Submit", 
            "title": "Afwijzen",
            "data": {"action": "reject"}
        }
    ]
}
```

#### **Flow 2: Uitgaande Peppol Facturen**

**Step 1: Dynamics 365 Trigger**
```
Flow Name: "Peppol - Uitgaande Factuur Verzending"
Trigger: "When a record is created or modified" (Dynamics 365)
Table: Invoices
Filter: Status eq 'Ready to Send'
```

**Step 2: Build UBL XML**
```
Action: "Compose"
Expression: [Complex XML construction - see template below]
```

**UBL XML Template Expression:**
```
concat('<?xml version="1.0" encoding="UTF-8"?>
<Invoice xmlns="urn:oasis:names:specification:ubl:schema:xsd:Invoice-2">
    <cbc:ID>', triggerOutputs()?['body/invoicenumber'], '</cbc:ID>
    <cbc:IssueDate>', formatDateTime(triggerOutputs()?['body/createdon'], 'yyyy-MM-dd'), '</cbc:IssueDate>
    <cac:AccountingSupplierParty>
        <cac:Party>
            <cbc:EndpointID schemeID="0208">', triggerOutputs()?['body/suppliervat'], '</cbc:EndpointID>
            <cac:PartyName>
                <cbc:Name>', triggerOutputs()?['body/suppliername'], '</cbc:Name>
            </cac:PartyName>
        </cac:Party>
    </cac:AccountingSupplierParty>
    <!-- Add more UBL elements as needed -->
</Invoice>')
```

**Step 3: Send to Peppol Access Point**
```
Action: "HTTP"
Method: POST
URI: https://demo-accesspoint.com/api/send
Headers:
- Content-Type: application/xml
- Authorization: Bearer [API_KEY]
Body: outputs('Compose')
```

**Step 4: Update Status**
```
Action: "Update a record" (Dynamics 365)
Record ID: triggerOutputs()?['body/invoiceid']
Status: "Sent via Peppol"
Sent Date: utcNow()
```

### 🧪 Testing Procedures

#### **Test Scenario 1: Inkomende Factuur**
1. **Setup**: Use Postman to simulate Peppol webhook
2. **Request**: POST to HTTP trigger URL
3. **Body**: Use UBL-Invoice-Sample.xml
4. **Expected**: Teams notification + Dynamics record created
5. **Verify**: Check Dynamics 365 for new invoice record

#### **Test Scenario 2: Uitgaande Factuur**  
1. **Setup**: Create manual invoice in Dynamics 365
2. **Trigger**: Set status to "Ready to Send"
3. **Expected**: HTTP call to access point + status update
4. **Verify**: Check flow run history for success

#### **Postman Test Collection**
```json
{
    "info": {
        "name": "Peppol E-facturatie Tests"
    },
    "item": [
        {
            "name": "Test Inkomende Factuur",
            "request": {
                "method": "POST",
                "header": [
                    {
                        "key": "Content-Type",
                        "value": "application/xml"
                    }
                ],
                "body": {
                    "mode": "raw",
                    "raw": "[Insert UBL-Invoice-Sample.xml here]"
                },
                "url": {
                    "raw": "[Your HTTP trigger URL]"
                }
            }
        }
    ]
}
```

### 📊 Demo Presentation Flow

#### **Recording Sequence for Video**
1. **Setup Shot** (30 sec): Show clean Power Automate interface
2. **Flow Overview** (1 min): Navigate through both flows at high level
3. **Inkomende Demo** (3 min): 
   - Trigger flow via Postman
   - Show real-time execution
   - Display Teams notification
   - Check Dynamics record
4. **Uitgaande Demo** (2 min):
   - Create invoice in Dynamics
   - Show automatic trigger
   - Display XML generation
   - Verify API call success
5. **Wrap-up** (30 sec): Show both completed flow runs

#### **Screen Recording Tips**
- **Browser Zoom**: Set to 125% for better visibility
- **Window Size**: 1920x1080 (full HD)
- **Mouse Highlighting**: Use yellow circle cursor
- **Speed**: Slow mouse movements, pause at key points
- **Audio**: Record separate track, sync in post-production

### 🔒 Security Considerations

#### **Production Environment Setup**
```
Security Measures:
- Use service accounts (not personal accounts)
- Implement proper API key management  
- Set up connection reference for reusability
- Enable data loss prevention policies
- Configure environment-specific variables
```

#### **Access Point Integration**
```
Recommended Providers (Belgium):
- Unimaze (Belgian provider)
- TIE Kinetix
- Tradeshift
- DigitalRain

Required from Provider:
- Sandbox/test environment
- API documentation
- Webhook endpoints
- Test BTW numbers
```

This technical setup guide provides everything needed to create a working demo environment for the E-facturatie video. The combination of real Power Automate flows with proper test data will create a compelling, authentic demonstration that builds trust with potential clients.
