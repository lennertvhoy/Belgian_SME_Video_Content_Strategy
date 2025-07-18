# Video 2: AI Document Intelligence - Complete Production Script
## "Van Factuur tot Inzicht: Automatiseer uw Crediteurenadministratie met Azure AI"

### 📋 Video Overview
- **Duration**: 8-10 minuten
- **Format**: How-to demonstratie met live AI processing
- **Target**: Financieel Manager, Hoofdboekhouder, CEO
- **Goal**: AI automation project leads + Azure AI service adoption

### 🎯 Key Messages
1. **Universeel probleem**: Manuele factuurverwerking is foutgevoelig en tijdrovend
2. **AI oplossing**: Azure Document Intelligence automatiseert extractie
3. **Business case**: 60-80% tijdsbesparing, minder fouten
4. **Haalbaarheid**: Prebuilt models werken out-of-the-box
5. **Integratie**: Naadloos met bestaande Power Automate workflows

### 📝 Detailed Script with Technical Demo

#### **HOOK & PROBLEEM (0:00 - 1:00)**
**Visual**: Chaos montage van papieren facturen, Excel sheets, e-mails
**Audio Script**:
> "Elke maand hetzelfde ritueel: stapels facturen, PDF's in verschillende formaten, 
> leveranciers die elk hun eigen lay-out gebruiken. Uw boekhouder typt data over, 
> maakt fouten, verliest tijd met zoeken naar BTW-nummers en bedragen.
> 
> Een bedrijf met 1.000 facturen per maand verliest gemakkelijk 40 uur per maand 
> aan manuele verwerking. Dat is €2.500 aan loonkosten, plus de fouten die leiden 
> tot verkeerde betalingen en gemiste kortingen.
> 
> Wat als ik u zeg dat Azure AI dit proces kan automatiseren? Niet 95%, maar 98% 
> accuraat. Elke factuur, ongeacht formaat of leverancier, in seconden verwerkt."

**Production Notes**:
- Start with relatable pain points
- Use real cost calculations for impact
- Show messy desk with paper invoices vs clean digital workflow
- Build urgency around manual processing costs

#### **OPLOSSING INTRODUCTIE (1:00 - 1:45)**
**Visual**: Azure AI Document Intelligence interface showcase
**Audio Script**:
> "Azure AI Document Intelligence is Microsoft's enterprise-ready oplossing voor 
> documentverwerking. Het gebruikt machine learning modellen die getraind zijn 
> op miljoenen documenten wereldwijd.
> 
> Het mooie? Er zijn prebuilt modellen specifiek voor facturen. Geen training nodig, 
> geen AI-expertise vereist. U laadt een factuur op, krijgt perfect gestructureerde 
> data terug. JSON-formaat, klaar voor integratie met elk systeem.
> 
> Ik ga nu live demonstreren hoe dit werkt, van ruwe PDF tot automatische 
> boekhouding in uw ERP-systeem."

**Demo Environment Requirements**:
```
Azure Services Required:
├── Azure AI Document Intelligence resource
├── Document Intelligence Studio access
├── Sample invoice PDFs (various formats)
├── Power Automate Premium license
└── Test ERP/accounting system (Dynamics 365)
```

#### **DEMO DEEL 1: AZURE AI SETUP (1:45 - 3:15)**
**Visual**: Live Azure portal configuration
**Audio Script**:
> "Eerst tonen we hoe eenvoudig de setup is. In de Azure portal creëer ik een 
> Document Intelligence resource. Let op hoe weinig configuratie er nodig is."

**Step-by-Step Demo Instructions**:

**Stap 1: Azure Resource Creation (45 seconden)**
```
Actions to Record:
1. Navigate to portal.azure.com
2. Click "Create a resource"
3. Search "Document Intelligence"
4. Select "Document Intelligence" service
5. Configure:
   - Subscription: Your test subscription
   - Resource Group: "DocumentAI-Demo"
   - Region: "West Europe" (GDPR compliance)
   - Name: "invoice-processing-ai"
   - Pricing Tier: "Free F0" (for demo)
6. Click "Review + Create"
7. Wait for deployment

Recording Script:
"Kijk hoe simpel dit is. Gewoon een resource aanmaken, West Europe voor 
GDPR-compliance, en zelfs een gratis tier om te testen."
```

**Stap 2: Document Intelligence Studio (45 seconden)**
```
Actions:
1. Navigate to documentintelligence.ai.azure.com
2. Sign in with Azure account
3. Select the created resource
4. Navigate to "Prebuilt models"
5. Click "Invoice" model
6. Show model capabilities overview

Recording Script:
"Document Intelligence Studio is de gebruiksvriendelijke interface. 
Hier zie je alle prebuilt modellen. Voor facturen is er een speciaal 
model dat al getraind is op duizenden factuurformaten."
```

#### **DEMO DEEL 2: LIVE INVOICE PROCESSING (3:15 - 5:45)**
**Visual**: Real-time document analysis and data extraction
**Audio Script**:
> "Nu de magie. Ik upload verschillende facturen - PDF, gescand papier, 
> zelfs foto's - en laat zien hoe accuraat de AI de data extraheert."

**Step-by-Step Processing Demo**:

**Stap 1: Upload Belgian Invoice PDF (90 seconden)**
```
Sample Invoice Requirements:
- Belgian supplier (BTW number starting with BE)
- Standard European invoice format
- Multiple line items
- Different currencies acceptable
- Various layouts (formal, simple, complex)

Demo Process:
1. Click "Analyze document" in Studio
2. Upload PDF file: "Factuur_Leverancier_BE123456.pdf"
3. Wait for processing (15-30 seconds)
4. Show real-time analysis progress
5. Display extracted results

Recording Script:
"Ik upload een echte Belgische factuur. Kijk hoe de AI elk veld herkent: 
leverancier, BTW-nummer, factuurregels, totalen. Zelfs de vervaldatum 
wordt automatisch geëxtraheerd."
```

**Stap 2: Results Analysis (90 seconders)**
```
Key Fields to Highlight:
├── Vendor Information:
│   ├── Name: Extracted text
│   ├── Address: Complete address parsing
│   └── VAT Number: BE-format validation
├── Invoice Details:
│   ├── Invoice Number: Unique identifier
│   ├── Issue Date: Date format conversion
│   └── Due Date: Payment terms calculation
├── Line Items:
│   ├── Description: Product/service details
│   ├── Quantity: Numeric extraction
│   ├── Unit Price: Currency formatting
│   └── Total: Calculation verification
└── Totals:
    ├── Subtotal: Pre-tax amount
    ├── VAT Amount: Tax calculation
    └── Total Amount: Final payable

Recording Script:
"Perfecte extractie! Elk veld correct herkend, bedragen berekend, 
datums in het juiste formaat. De confidence score toont 98% 
zekerheid - hoger dan menselijke accuraatheid."
```

**Stap 3: Multiple Format Test (90 seconden)**
```
Test Documents:
1. Scanned paper invoice (photo quality)
2. Email PDF attachment (different layout)
3. Non-standard format (handwritten elements)

Demo Process:
1. Upload each document type
2. Show processing for different layouts
3. Compare extraction accuracy
4. Highlight handling of edge cases

Recording Script:
"Verschillende formaten, verschillende leveranciers - de AI past zich 
automatisch aan. Zelfs handgeschreven notities worden herkend. 
Dit werkt met elke factuur die u ontvangt."
```

#### **DEMO DEEL 3: POWER AUTOMATE INTEGRATION (5:45 - 8:00)**
**Visual**: Complete automation workflow demonstration
**Audio Script**:
> "Extractie is één ding, maar echte waarde komt van volledige automatisering. 
> Ik laat zien hoe Power Automate dit integreert met uw bestaande systemen."

**Complete Workflow Demo**:

**Stap 1: Email Trigger Setup (45 seconden)**
```
Power Automate Flow Design:
1. Trigger: "When a new email arrives" (Outlook)
2. Condition: "Has attachments" = true
3. Filter: Attachment type = PDF
4. Action: Save attachment to SharePoint

Recording Script:
"De flow start zodra een e-mail met PDF-bijlage binnenkomt op uw 
crediteuren e-mailadres. Automatische herkenning van facturen."
```

**Stap 2: AI Document Analysis (60 seconders)**
```
Integration Steps:
1. Action: "Analyze document" (Document Intelligence connector)
2. Input: Email attachment content
3. Model: Prebuilt Invoice model
4. Configuration: Return confidence scores
5. Output: Structured JSON data

Recording Script:
"Power Automate stuurt de PDF direct naar Azure AI. In enkele seconden 
krijgen we gestructureerde data terug. Kijk naar deze JSON-output - 
elke factuurlijn perfect geparseerd."
```

**Stap 3: Business Logic & Validation (75 seconden)**
```
Validation Rules:
1. Condition: Confidence score > 85%
2. Condition: Supplier exists in master data
3. Condition: Amount within expected range
4. Action: Create approval task if amount > €1000

Demo Process:
1. Show high-confidence automatic processing
2. Demo manual review for low confidence
3. Display supplier validation logic
4. Show approval workflow for large amounts

Recording Script:
"Intelligente validatie voorkomt fouten. Hoge zekerheid? Direct verwerken. 
Onbekende leverancier? Naar review. Groot bedrag? Automatische goedkeuring 
via Teams. Volledige controle met minimale handmatige interventie."
```

**Stap 4: ERP Integration (60 seconden)**
```
Final Processing:
1. Action: "Create record" in Dynamics 365/ERP
2. Mapping: JSON fields to ERP fields
3. Action: Update supplier master data
4. Action: Send Teams notification
5. Action: File original in SharePoint

Recording Script:
"En klaar! Factuur automatisch aangemaakt in uw ERP-systeem, leverancier 
bijgewerkt, team geïnformeerd via Teams. Van e-mail tot boekhouding in 
onder de 2 minuten, zonder menselijke tussenkomst."
```

#### **BUSINESS CASE & ROI (8:00 - 8:45)**
**Visual**: Cost savings calculator and efficiency metrics
**Audio Script**:
> "Laten we rekenen. 1.000 facturen per maand, 3 minuten handmatige verwerking 
> per factuur. Dat is 50 uur per maand aan work. Met AI: 30 seconden per factuur, 
> 8 uur per maand. Besparing: 42 uur per maand.
> 
> Aan €25 per uur betekent dit €1.050 besparing per maand, €12.600 per jaar. 
> Azure AI Document Intelligence kost €1.50 per 1.000 pagina's. Voor 1.000 
> facturen: €1.50 per maand.
> 
> ROI: €12.600 besparing minus €18 kosten = €12.582 netto besparing per jaar. 
> Dat is 700% ROI, zonder de verbeterde accuraatheid en snellere betalingen 
> mee te rekenen."

**Visual Requirements**:
- Animated calculator showing time savings
- Cost comparison table (manual vs AI)
- ROI percentage display (700%)
- Error reduction statistics

#### **ADVANCED FEATURES PREVIEW (8:45 - 9:15)**
**Visual**: Custom model training interface
**Audio Script**:
> "Voor bedrijven met unieke documentformaten kan Azure AI custom modellen 
> trainen. Met slechts 5 voorbeelddocumenten creëert u een model voor uw 
> specifieke lay-outs. Contracten, orderbevestigingen, pakbonnen - 
> dezelfde technologie, aangepast aan uw processen."

**Demo Elements**:
- Show custom model training interface
- Display training progress simulation
- Highlight enterprise scalability options
- Mention compliance and security features

#### **CALL TO ACTION (9:15 - 10:00)**
**Visual**: Contact information and demo offer
**Audio Script**:
> "AI is geen toekomstmuziek meer. Het is beschikbaar vandaag, betaalbaar 
> voor elke KMO, en kan uw financiële processen revolutioneren.
> 
> Benieuwd hoeveel u kunt besparen met uw eigen facturen? Vraag onze gratis 
> 'Document AI Proof of Concept' aan. We analyseren uw documenten en tonen 
> de exacte verwachte besparingen.
> 
> Boek via de link in de beschrijving, of bel direct. Laat AI het zware werk 
> doen, zodat u zich kunt focussen op uw core business."

**CTA Elements**:
- "Gratis Proof of Concept" booking link
- "Document AI ROI Calculator" download
- Contact phone number overlay
- Email address display

### 🛠️ Technical Demo Environment Setup

#### **Required Azure Resources**
```
Azure Services:
├── Document Intelligence (Free tier: 500 pages/month)
├── Storage Account (for document storage)
├── Power Automate Premium (€15/user/month)
└── Optional: Logic Apps (advanced workflows)

Cost Estimate for Demo:
├── Azure AI Document Intelligence: €0 (free tier)
├── Storage: €1/month (minimal usage)
├── Power Automate: €15/month (existing license)
└── Total: ~€16/month for full demo capability
```

#### **Sample Documents Preparation**
```
Required Invoice Types:
├── Standard Belgian B2B Invoice (PDF)
├── Scanned paper invoice (JPG/PNG)
├── Email-generated invoice (different layout)
├── Multi-page invoice (with line items)
├── Non-standard format (handwritten elements)
└── International invoice (for comparison)

Document Sources:
├── Create realistic dummy invoices
├── Use public invoice templates
├── Scan real invoices (anonymized)
└── Generate test data with Belgian VAT formats
```

#### **Power Automate Flow Templates**
```
Flow 1: "Email Invoice Processing"
├── Trigger: When email received (invoices@company.com)
├── Condition: Has PDF attachment
├── Action: Save to SharePoint
├── Action: Analyze with Document Intelligence
├── Condition: Confidence > 85%
├── Action: Create ERP record
└── Action: Send Teams notification

Flow 2: "Batch Invoice Processing"
├── Trigger: When files added to SharePoint folder
├── Action: For each file in folder
├── Action: Analyze with Document Intelligence
├── Action: Store results in database
└── Action: Generate processing report

Flow 3: "Manual Review Workflow"
├── Trigger: HTTP request (from low-confidence processing)
├── Action: Create approval task in Teams
├── Action: Wait for approval
├── Condition: If approved
├── Action: Process to ERP
└── Action: Archive document
```

### 📊 Success Metrics & KPIs

#### **Technical Performance**
```
ACCURACY TARGETS:
├── Field extraction accuracy: >95%
├── Amount recognition: >98%
├── Date parsing: >97%
├── Supplier identification: >90%
└── Overall document confidence: >90%

PERFORMANCE TARGETS:
├── Processing time: <30 seconds per document
├── End-to-end automation: <2 minutes
├── Manual intervention: <10% of documents
├── Error rate: <2% (vs 8-12% manual entry)
└── Cost per document: <€0.05
```

#### **Business Impact Measurements**
```
EFFICIENCY GAINS:
├── Time reduction: 85% (from 3min to 30sec per invoice)
├── Staff reallocation: 42 hours/month to higher-value tasks
├── Processing speed: Same-day vs 3-5 day manual processing
├── Error reduction: 80% fewer payment mistakes
└── Cost savings: €12,000+ annually for 1000 invoices/month

LEAD GENERATION TARGETS:
├── Consultation requests: 30+ per month
├── Proof of Concept demos: 10+ per month
├── Qualified AI automation leads: 15+ per month
├── Average project value: €25,000 (AI + automation)
└── Conversion rate: 20% from video to consultation
```

This comprehensive script provides everything needed to create a compelling demonstration of Azure AI Document Intelligence that will generate high-quality leads for AI automation projects while educating potential clients about the practical benefits of document processing automation.
