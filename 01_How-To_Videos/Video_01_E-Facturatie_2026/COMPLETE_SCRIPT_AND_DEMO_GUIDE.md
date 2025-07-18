# Video 1: E-facturatie 2026 - Complete Production Script
## "Maak uw Bedrijf Klaar voor 2026: Praktische Gids voor Verplichte E-facturatie"

### 📋 Video Overview
- **Duration**: 8-10 minuten
- **Format**: How-to demonstratie
- **Target**: CEO/Zaakvoerder, Financieel Manager
- **Goal**: Lead generation voor e-facturatie implementatie projecten

### 🎯 Key Messages
1. **Urgentie**: 1 januari 2026 deadline is onvermijdelijk
2. **Consequenties**: BTW-aftrek verlies bij non-compliance  
3. **Opportuniteit**: Automatisering en fiscale voordelen
4. **Haalbaarheid**: Power Automate maakt het toegankelijk

### 📝 Detailed Script with Timing

#### **INTRO (0:00 - 0:30)**
**Visual**: Animated countdown naar 1 januari 2026
**Audio Script**: 
> "Vanaf 1 januari 2026 verandert de manier waarop u factureert fundamenteel. 
> Een PDF via e-mail volstaat niet meer. De vraag is niet óf u moet veranderen, 
> maar hoe u dit slim en voordelig doet. In deze video toon ik u stap voor stap 
> hoe u met Power Automate en Peppol niet alleen compliant wordt, maar ook 
> uw facturatieproces volledig automatiseert."

**Production Notes**:
- Use urgency-creating visuals (countdown timer)
- Professional but approachable tone
- Clear value proposition in first 15 seconds

#### **PROBLEEM DEFINITIE (0:30 - 1:30)**
**Visual**: Side-by-side comparison oude vs nieuwe situatie
**Audio Script**:
> "Wat betekent dit concreet? Momenteel verstuurt u facturen als PDF-bijlage. 
> Vanaf 2026 moet elke factuur gestructureerde data bevatten volgens de Peppol-standaard.
> 
> Hier komt de pijn: Als u een inkomende factuur ontvangt die niet aan de nieuwe 
> norm voldoet, kunt u de BTW daarop niet meer aftrekken. Voor een KMO kan dit 
> duizenden euro's per jaar kosten.
> 
> Maar er is goed nieuws. De overheid stimuleert deze transitie met interessante 
> fiscale voordelen: 20% verhoogde investeringsaftrek en 120% kostenaftrek voor 
> abonnementsformules."

**Demo Setup Required**:
- Screenshot van huidige PDF-factuur
- Mockup van gestructureerde Peppol-factuur
- Slide met fiscale voordelen (exacte percentages)

#### **OPLOSSING INTRODUCTIE (1:30 - 2:30)**
**Visual**: Peppol 4-corner model diagram
**Audio Script**:
> "De oplossing ligt in het Peppol-netwerk. Peppol is als een beveiligd telecomnetwerk, 
> maar dan voor facturen. Vier partijen werken samen: u als verzender, uw Access Point, 
> het Access Point van uw klant, en uw klant zelf.
> 
> Dit klinkt complex, maar met Power Automate kunnen we dit volledig automatiseren. 
> U hoeft alleen maar uw normale facturatieproces te volgen, de rest gebeurt automatisch."

**Demo Setup Required**:
- Animated Peppol 4-corner diagram
- Power Automate logo integration
- Flow diagram van automatisering

#### **DEMO DEEL 1: INKOMENDE FACTUREN (2:30 - 6:00)**
**Visual**: Live Power Automate demo
**Audio Script**:
> "Laten we beginnen met inkomende facturen. Ik toon u nu een Power Automate flow 
> die automatisch start zodra een Peppol-factuur binnenkomt."

**Step-by-Step Demo Instructions**:

**Setup Requirements**:
```
Power Automate Premium account
Test Peppol Access Point (demo environment)  
Dynamics 365 / test ERP system
Microsoft Teams (notifications)
Sample UBL-XML facturen
```

**Flow Demo Script**:
1. **Trigger Setup** (2:30 - 3:00)
   - Show "When a HTTP request is received" trigger
   - Explain webhook integration with Peppol Access Point
   - Demo: Simulated inkomende Peppol factuur

2. **Data Parsing** (3:00 - 4:00)
   - Show "Parse JSON" action
   - Display UBL-XML structure on screen
   - Highlight key fields: leverancier, bedrag, BTW, lijn-items
   - **Script**: "Kijk hoe gestructureerd deze data is vergeleken met een PDF"

3. **Business Logic** (4:00 - 5:00)
   - Show "Condition" action voor leverancier validatie
   - Demo: Check if supplier exists in ERP system
   - Show "Create record" action voor approved facturen
   - **Script**: "Automatische validatie voorkomt fouten en fraude"

4. **Notification** (5:00 - 6:00)
   - Show Teams notification action
   - Demo: Adaptive card met factuur details
   - Include approve/reject buttons
   - **Script**: "Uw boekhouder krijgt directe notificatie met alle details"

#### **DEMO DEEL 2: UITGAANDE FACTUREN (6:00 - 8:30)**
**Visual**: Live demo uitgaande flow
**Audio Script**:
> "Nu de omgekeerde richting. Wanneer u een factuur aanmaakt in uw ERP-systeem, 
> zorgt Power Automate ervoor dat deze automatisch via Peppol verstuurd wordt."

**Step-by-Step Demo Instructions**:

1. **ERP Trigger** (6:00 - 6:30)
   - Show "When a record is created" trigger (Dynamics 365)
   - Demo: Create new invoice in ERP
   - **Script**: "Zodra u 'versturen' klikt, start de automatisering"

2. **Data Transformation** (6:30 - 7:30)
   - Show "Compose" action voor UBL conversie
   - Display JSON transformation van ERP naar Peppol format
   - Highlight BIS 3.0 compliance
   - **Script**: "Power Automate vertaalt uw factuurdata naar de vereiste Peppol-standaard"

3. **Peppol Transmission** (7:30 - 8:00)
   - Show HTTP action naar Access Point API
   - Demo: Authentication met API key
   - Show successful transmission response
   - **Script**: "En klaar! Uw factuur is nu onderweg via het Peppol-netwerk"

4. **Confirmation** (8:00 - 8:30)
   - Show status update in ERP
   - Demo: Email confirmation naar verkoper
   - **Script**: "Volledige traceerbaarheid: u weet altijd wanneer uw factuur aangekomen is"

#### **FISCALE VOORDELEN (8:30 - 9:00)**
**Visual**: Animated cost savings calculator
**Audio Script**:
> "En nu het mooiste: de overheid helpt u financieel. Met de 20% verhoogde investeringsaftrek 
> kunt u meer aftrekken van uw investering in dit systeem. En abonnementskosten voor 
> Access Points zijn 120% aftrekbaar, wat betekent dat u meer kunt aftrekken dan u betaalt."

**Visual Requirements**:
- Calculator animation showing:
  - Investment: €5,000 (Power Automate setup)
  - Normal aftrek: €1,050 (21% BTW)
  - Verhoogde aftrek: €1,260 (20% extra)
  - Annual savings demonstration

#### **CALL TO ACTION (9:00 - 9:30)**
**Visual**: Contact form/calendar booking interface
**Audio Script**:
> "E-facturatie is meer dan compliance - het is de start van echte automatisering. 
> Wacht niet tot eind 2025 wanneer iedereen haast heeft. Start nu en profiteer 
> van de fiscale voordelen.
> 
> Download onze gratis E-facturatie Checklist via de link in de beschrijving, 
> of boek direct een intakegesprek om uw specifieke situatie te analyseren."

**CTA Elements**:
- Download link: "E-facturatie Checklist 2026"
- Booking link: "Gratis Intakegesprek" (Calendly/scheduling tool)
- Contact details overlay
- Subscribe button voor meer content

### 🛠️ Technical Demo Setup Guide

#### **Pre-Production Checklist**
- [ ] Power Automate Premium licentie actief
- [ ] Test ERP environment (Dynamics 365 trial)
- [ ] Peppol Access Point demo account
- [ ] Sample UBL-XML bestanden
- [ ] Microsoft Teams configured
- [ ] Screen recording setup (OBS with scenes)
- [ ] Audio testing completed

#### **Demo Environment Setup**

**Power Automate Flows te creëren**:
1. **"Inkomende Peppol Factuur"**
   ```
   Trigger: HTTP Request (webhook simulation)
   Action 1: Parse JSON (UBL structure)
   Action 2: Condition (supplier validation)
   Action 3: Create Dynamics record
   Action 4: Send Teams notification
   ```

2. **"Uitgaande Peppol Factuur"**
   ```
   Trigger: Dynamics record created
   Action 1: Compose UBL transformation
   Action 2: HTTP POST to Peppol API
   Action 3: Update record status
   Action 4: Send confirmation email
   ```

#### **Required Assets**
- Sample XML files (UBL 2.1 format)
- Peppol Access Point API documentation
- Dynamics 365 demo data
- Teams notification templates
- Cost calculation spreadsheets

#### **Recording Setup**
**OBS Scenes**:
1. **Full Screen**: Voor intro en outro
2. **Browser Window**: Power Automate interface
3. **Split Screen**: Browser + PowerPoint slides
4. **Picture-in-Picture**: Webcam + demo screen

**Audio Setup**:
- Professional USB microphone
- Quiet recording environment
- Script timing practice (aim for 8-9 minutes)
- Backup audio recording (phone/Audacity)

### 📊 Success Metrics
- **Primary**: Lead generation (downloads + bookings)
- **Engagement**: Comments met specifieke vragen
- **Education**: Reduction in support calls about e-facturatie
- **Authority**: Shares door industry influencers

### 🔄 Post-Production Checklist
- [ ] Export in 1080p H.264
- [ ] Upload to YouTube met SEO-optimized beschrijving
- [ ] Create LinkedIn video post
- [ ] Add to company website blog
- [ ] Include in email newsletter
- [ ] Track conversion metrics via Google Analytics

Dit script geeft je een complete blueprint voor een professionele, educatieve video die direct leads zal genereren voor e-facturatie projecten bij Belgische KMO's.
