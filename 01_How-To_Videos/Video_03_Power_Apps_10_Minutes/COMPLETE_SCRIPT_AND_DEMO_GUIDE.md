# Video 3: Power Apps - Complete Production Script
## "Bouw uw Eerste Bedrijfsapp in 10 Minuten: Low-Code met Microsoft Power Apps"

### 📋 Video Overview
- **Duration**: 8-10 minuten
- **Format**: Live development demonstration
- **Target**: CEO/Zaakvoerder, Operationeel Manager
- **Goal**: Power Platform consultancy leads + citizen developer enablement

### 🎯 Strategic Messaging
1. **Speed**: Professional app development in minutes, not months
2. **Accessibility**: No coding required, business users can build
3. **Integration**: Seamless connection with Microsoft 365 ecosystem
4. **Cost-Effectiveness**: Fraction of traditional development costs
5. **Scalability**: Start simple, grow with business needs

### 📝 Complete Script with Detailed Demo Instructions

#### **HOOK & INTRO (0:00 - 0:45)**
**Visual**: Split screen showing Excel chaos vs clean mobile app
**Audio Script**:
> "Hoeveel bedrijfsprocessen verlopen nog steeds via papier of chaotische Excel-sheets? 
> Inspectierapporten, onkostennota's, vakantieaanvragen... U weet dat dit inefficiënt is, 
> maar custom software kost tienduizenden euro's en maanden ontwikkeling.
> 
> Wat als ik u zeg dat u in de komende 10 minuten een professionele bedrijfsapp 
> kunt bouwen? Zonder programmeerkennis, zonder externe developers, gewoon met 
> Microsoft Power Apps. Let op, dit is geen theorie - ik bouw live mee!"

**Production Notes**:
- Start with relatable business pain points
- Show real Excel spreadsheet mess
- Counter with clean, professional app interface
- Create urgency and excitement for live demo

#### **PROBLEEM SCHETS (0:45 - 1:30)**
**Visual**: Sequence showing typical business process pain points
**Audio Script**:
> "Neem een typisch voorbeeld: IT-helpdesk tickets. Momenteel gebeurt dit via e-mail, 
> Word-documenten of Excel-lijsten. Geen prioritering, geen status tracking, 
> geen rapportage. Chaos.
> 
> Traditionele softwareontwikkeling? Minstens €15.000 en 3 maanden wachten. 
> En dan nog eens €2.000 per maand voor onderhoud. Voor een KMO is dat 
> vaak te duur en te traag.
> 
> Power Apps verandert dit spel compleet. Dezelfde functionaliteit, professionele 
> uitstraling, maar dan in minuten gebouwd en voor een fractie van de kost."

**Visual Requirements**:
- Screenshots of chaotic email threads
- Excel spreadsheet with inconsistent data
- Cost comparison: traditional vs Power Apps
- Timeline comparison: months vs minutes

#### **DEMO SETUP (1:30 - 2:00)**
**Visual**: Clean Power Apps interface introduction
**Audio Script**:
> "Ik ga nu live een complete IT-helpdesk app bouwen. We starten helemaal vanaf nul. 
> Geen voorbereid werk, geen hidden tricks. Pure Power Apps magie.
> 
> Voor deze demo gebruik ik een standaard Microsoft 365 Business Premium licentie. 
> Dat is wat de meeste KMO's al hebben. Geen extra investeringen nodig."

**Demo Environment Preparation**:
```
Required Setup:
├── Microsoft 365 Business Premium account
├── Power Apps maken portal: make.powerapps.com
├── SharePoint Online access
├── Clean browser session (geen cached data)
└── Screen recording software (OBS) configured
```

#### **DEMO DEEL 1: DATA FOUNDATION (2:00 - 3:30)**
**Visual**: Live SharePoint list creation
**Audio Script**:
> "Elke app heeft data nodig. In plaats van een complexe database, gebruiken we 
> SharePoint Online. Dat is inbegrepen in uw Microsoft-licentie en perfect 
> geïntegreerd."

**Step-by-Step Demo Instructions**:

**Stap 1: SharePoint Lijst Aanmaken (30 seconden)**
```
Actions to Record:
1. Navigate to SharePoint Online
2. Click "New" → "List"
3. Choose "Blank list"
4. Name: "IT Helpdesk Tickets"
5. Description: "Beheer van IT-problemen en aanvragen"
```

**Stap 2: Kolommen Toevoegen (60 seconden)**
```
Required Columns:
├── Title (Single line text) - Default, rename to "Probleem Beschrijving"
├── Categorie (Choice): Hardware, Software, Netwerk, Toegang, Anders
├── Prioriteit (Choice): Laag, Normaal, Hoog, Kritiek
├── Status (Choice): Nieuw, In Behandeling, Wacht op Info, Opgelost
├── Aanvrager (Person) - Current user default
├── Toegewezen Aan (Person) - Optional
├── Aangemaakt Op (Date) - Auto-fill creation date
└── Notities (Multiple lines of text)

Recording Script:
"Ik voeg snel de essentiële velden toe. Categorie voor organisatie, 
prioriteit voor planning, status voor opvolging. Let op hoe intuïtief dit is."
```

**Stap 3: Testdata Toevoegen (30 seconden)**
```
Sample Records to Create:
1. "Printer werkt niet" | Hardware | Hoog | Nieuw
2. "Wachtwoord vergeten" | Toegang | Normaal | In Behandeling  
3. "Excel crasht constant" | Software | Hoog | Nieuw

Recording Script:
"Even wat testdata toevoegen zodat onze app niet leeg is."
```

#### **DEMO DEEL 2: APP GENERATIE (3:30 - 5:00)**
**Visual**: Power Apps automatic app generation
**Audio Script**:
> "Nu komt de magie. Power Apps kan automatisch een volledige app genereren 
> op basis van onze data. Geen code schrijven, geen design werk. Gewoon klikken."

**Step-by-Step Instructions**:

**Stap 1: Power Apps Openen (15 seconden)**
```
Actions:
1. Navigate to make.powerapps.com
2. Select correct environment (default)
3. Click "Create" in left navigation
4. Choose "Start from data"
```

**Stap 2: Data Source Connecteren (30 seconden)**
```
Actions:
1. Click "SharePoint" connector
2. Select SharePoint site
3. Choose "IT Helpdesk Tickets" list
4. Click "Connect"

Recording Script:
"Ik selecteer onze net aangemaakte SharePoint lijst. Power Apps 
detecteert automatisch de structuur en veldtypes."
```

**Stap 3: App Generatie (45 seconden)**
```
Process:
1. Power Apps analyzes data structure
2. Generates three screens automatically:
   - Browse screen (list view)
   - Detail screen (individual record)
   - Edit screen (form for updates)
3. Applies responsive design
4. Creates navigation logic

Recording Script:
"Kijk hoe snel dit gaat! Power Apps bouwt automatisch drie schermen: 
een overzicht, detailweergave en bewerkingsformulier. Alles responsive, 
alles functioneel."
```

**Stap 4: Eerste Test (30 seconden)**
```
Actions:
1. Click "Play" button (▶️)
2. Navigate through generated app
3. Show browse, detail, edit functionality
4. Demonstrate responsiveness

Recording Script:
"En het werkt al! Volledig functionele app in minder dan 2 minuten. 
Maar we gaan dit professioneler maken."
```

#### **DEMO DEEL 3: CUSTOMIZATION (5:00 - 7:30)**
**Visual**: Live app customization and enhancement
**Audio Script**:
> "De gegenereerde app is een perfecte basis, maar nu maken we het echt 
> geschikt voor dagelijks gebruik. Huisstijl, gebruiksvriendelijkheid, 
> en slimme functies."

**Step-by-Step Customization**:

**Stap 1: Branding Toepassen (45 seconden)**
```
Customizations:
1. Navigate to "Tree view" → "App"
2. Change app name to "IT Helpdesk"
3. Upload company logo
4. Modify color theme:
   - Primary: Company brand color
   - Accent: Complementary color
5. Update icons and styling

Recording Script:
"Eerst de huisstijl. Logo uploaden, kleuren aanpassen aan uw 
bedrijfsidentiteit. Dit geeft direct een professionele uitstraling."
```

**Stap 2: User Experience Verbeteren (60 seconders)**
```
Enhancements:
1. Edit Form Screen:
   - Reorder fields logically
   - Set "Aanvrager" to User() function (auto-fill current user)
   - Make "Aangemaakt Op" field auto-populate with Now()
   - Hide system fields from user

2. Browse Screen:
   - Modify gallery layout for better readability
   - Add status color coding (red for critical, green for resolved)
   - Improve search functionality

Recording Script:
"Nu gebruiksvriendelijker maken. De aanvrager wordt automatisch ingevuld 
met de huidige gebruiker. Status krijgt kleurcoding voor snelle visuele 
identificatie."
```

**Stap 3: Geavanceerde Functies (45 seconden)**
```
Advanced Features:
1. Add camera control for photo attachments:
   - Insert → Media → Camera
   - Connect to attachment field
   
2. Add email notification:
   - Insert → AI Builder → Send email action
   - Trigger on new ticket creation
   
3. Add conditional logic:
   - Show "Toegewezen Aan" only if status = "In Behandeling"

Recording Script:
"En nu wat geavanceerde features. Camera functie voor foto's van problemen. 
Automatische e-mail notificaties. Allemaal zonder één regel code te schrijven!"
```

#### **DEMO DEEL 4: PUBLISHING & SHARING (7:30 - 8:30)**
**Visual**: App publication and distribution
**Audio Script**:
> "De app is klaar, maar hoe krijgen uw medewerkers er toegang toe? 
> Power Apps maakt dit supergemakkelijk."

**Step-by-Step Publication**:

**Stap 1: App Publiceren (20 seconden)**
```
Actions:
1. Click "Publish" button
2. Add version notes: "Initial IT Helpdesk app"
3. Confirm publication
4. Wait for processing completion

Recording Script:
"Publiceren is één klik. Power Apps maakt de app beschikbaar 
in de cloud voor al uw gebruikers."
```

**Stap 2: Delen met Team (40 seconders)**
```
Sharing Process:
1. Click "Share" button
2. Add users/groups:
   - IT Team (edit permissions)
   - All Employees (use permissions)
3. Set appropriate permission levels
4. Send invitation emails

Recording Script:
"Delen is net zo makkelijk. IT-team krijgt volledige toegang, 
andere medewerkers kunnen alleen tickets aanmaken en bekijken."
```

**Stap 3: Mobile Access Demo (30 seconders)**
```
Mobile Demonstration:
1. Show Power Apps mobile app download
2. Demonstrate app running on phone
3. Show offline capabilities
4. Display responsive design

Recording Script:
"En het mooiste: automatisch beschikbaar op alle devices. 
Desktop, tablet, smartphone - altijd dezelfde ervaring."
```

#### **BUSINESS CASE & ROI (8:30 - 9:15)**
**Visual**: Cost comparison and benefits summary
**Audio Script**:
> "Laten we even rekenen. Traditionele ontwikkeling: €15.000 en 3 maanden. 
> Power Apps: €10 per gebruiker per maand en 10 minuten bouwtijd.
> 
> Voor een team van 20 medewerkers betekent dit €200 per maand versus 
> een eenmalige investering van €15.000. Break-even na 6 jaar, maar u 
> heeft de oplossing vandaag al.
> 
> Belangrijker nog: geen vendor lock-in, volledige controle, en u kunt 
> zelf aanpassingen maken wanneer uw proces evolueert."

**Visual Requirements**:
- Cost comparison table
- ROI calculation animation
- Timeline comparison graphic
- Benefits checklist

#### **CALL TO ACTION (9:15 - 10:00)**
**Visual**: Contact information and next steps
**Audio Script**:
> "Dit was slechts een simpel voorbeeld. Power Apps kan veel complexere 
> processen automatiseren: goedkeuringsworkflows, integraties met externe 
> systemen, geavanceerde rapportage.
> 
> Heeft u een specifiek bedrijfsproces dat u wilt digitaliseren? 
> Boek onze gratis 'Power Platform Ideation Workshop'. In 2 uur tijd 
> analyseren we uw proces en bouwen een prototype.
> 
> Link in de beschrijving, of bel direct naar ons kantoor. 
> Laat de digitale transformatie niet langer op zich wachten!"

**CTA Elements**:
- Workshop booking link (Calendly)
- Phone number overlay
- Website URL
- Download: "Power Apps Starter Guide"

### 🛠️ Technical Setup Requirements

#### **Pre-Demo Preparation Checklist**
```
ACCOUNTS & LICENSES:
[ ] Microsoft 365 Business Premium (or Power Apps per-user license)
[ ] Power Apps maker portal access verified
[ ] SharePoint Online permissions confirmed
[ ] Test tenant prepared (clean environment)

RECORDING SETUP:
[ ] OBS Studio configured with scenes
[ ] Audio levels tested and optimized
[ ] Multiple monitor setup (demo + notes)
[ ] Backup recording method ready
[ ] Internet connection stability verified

CONTENT PREPARATION:
[ ] Company branding assets ready (logo, colors)
[ ] Sample data prepared for quick entry
[ ] Troubleshooting scenarios practiced
[ ] Timing rehearsed (aim for 8-9 minutes)
```

#### **OBS Recording Scenes Configuration**
```
SCENE 1: "Full Desktop"
├── Display Capture: Primary monitor (1920x1080)
├── Audio: Microphone + system audio
├── Overlay: Company logo (lower right)
└── Purpose: Intro/outro + overview shots

SCENE 2: "Browser Window"
├── Window Capture: Chrome/Edge browser
├── Crop: Remove browser chrome for clean look
├── Audio: Microphone only
└── Purpose: Power Apps development focus

SCENE 3: "Split Screen"
├── Left: Browser window (Power Apps)
├── Right: PowerPoint slides (explanations)
├── Audio: Microphone + subtle background music
└── Purpose: Explanation + demonstration

SCENE 4: "Mobile Demo"
├── Phone Screen Mirroring: Via USB or wireless
├── Background: Neutral gradient
├── Overlay: "Mobile Preview" label
└── Purpose: Cross-device demonstration
```

#### **Backup Plans & Troubleshooting**
```
COMMON ISSUES & SOLUTIONS:

Power Apps Loading Slowly:
├── Pre-load in browser tabs
├── Clear browser cache before recording
├── Use incognito/private mode
└── Have screenshots ready as backup

SharePoint Connection Errors:
├── Verify site permissions beforehand
├── Test data connection in advance
├── Prepare alternative data source (Excel)
└── Have PowerPoint slides explaining process

Demo Environment Issues:
├── Prepare multiple tenant accounts
├── Have pre-built app as backup
├── Record key sequences separately
└── Practice reset procedures

Audio/Video Problems:
├── Record system audio separately
├── Use wireless microphone backup
├── Have written script available
└── Prepare for post-production fixes
```

### 📊 Success Metrics for This Video

#### **Engagement Targets**
```
VIEWERSHIP GOALS:
├── YouTube: 2,000+ views in first month
├── LinkedIn: 500+ views per post
├── Website: 15% increase in Power Apps page traffic
└── Overall: 50+ workshop bookings from video

CONTENT PERFORMANCE:
├── Watch time: 75%+ completion rate
├── Engagement: 8%+ like rate, 3%+ comment rate
├── Shares: 50+ professional shares
└── Click-through: 5%+ CTA click rate

BUSINESS IMPACT:
├── Lead quality: 25+ qualified Power Apps prospects
├── Project pipeline: €50,000+ in Power Platform opportunities
├── Brand authority: 10+ LinkedIn thought leadership comments
└── Customer education: 30% reduction in "What is Power Apps?" calls
```

This comprehensive script provides everything needed to create a compelling Power Apps demonstration that will generate qualified leads while educating potential clients about the power and accessibility of low-code development.
