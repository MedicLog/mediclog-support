# MedicLog User Guide

**Version:** 0.9β (TestFlight)  
**Last Updated:** January 18, 2026

---

## Table of Contents

1. [Getting Started](#getting-started)
2. [Starting a Call](#starting-a-call)
3. [Adding Entries](#adding-entries)
4. [Radio Report (MIST Format)](#radio-report-mist-format)
5. [Ending a Call](#ending-a-call)
6. [Exporting Data](#exporting-data)
7. [Settings](#settings)
8. [Apple Watch Features](#apple-watch-features)
9. [Tips for Field Use](#tips-for-field-use)

---

## Getting Started

### Installing MedicLog

1. Install **TestFlight** from the App Store
2. Accept the TestFlight invitation email
3. Open TestFlight and install **MedicLog**
4. Launch MedicLog and complete initial setup

### First Launch

On first launch, you'll be prompted to configure:

- **User ID** - Your agency ID number (e.g., "A123")
- **User Name** - Your full name (e.g., "Jane Doe")
- **Unit Number** - Your ambulance/truck designation (e.g., "M-12")

These settings ensure proper attribution of all logged interventions. You can change these anytime in Settings.

---

## Starting a Call

### From iPhone

1. Open MedicLog
2. Tap **"Start New Call"** on the home screen
3. Enter the **Run Number** (e.g., E2026012345)
   - **Tip:** Paste from Messages - MedicLog automatically extracts the run number from dispatch text
4. The call session begins with automatic timestamping

### From Apple Watch

1. Open MedicLog on your watch
2. Tap **"START CALL"**
3. Enter the run number using voice or scribble
4. If iPhone is unavailable, tap **"Start Anyway"** for offline mode

**Note:** Watch sync is active but voice input features are limited in this beta version.

---

## Adding Entries

MedicLog supports four types of entries:

### 1. Medications

**Quick Entry (Recommended for field use):**

1. Tap the **medication button** (e.g., "Epi 1:10,000", "Versed")
2. Confirm or adjust the pre-filled:
   - **Dose** (default dose shown)
   - **Route** (tap to change if needed)
3. Add optional **Notes**
4. Tap **"Add Entry"**

**Manual Entry:**

1. Tap **"+ Add Entry"**
2. Select **"Medication"**
3. Choose medication from the 37-medication formulary
4. Enter dose, route, and notes
5. Tap **"Save"**

**Medication Timers:**

Some medications automatically start countdown timers:
- **Epinephrine (IV):** 4-minute timer for next dose
- **Fentanyl/Versed:** 10-minute reassessment timer
- **Albuterol:** 5-minute treatment timer
- **NTG:** 4-minute timer

**Available Medications (37 total):**

*Cardiac:*
- Adenosine, Amiodarone, Atropine, Epi 1:10,000, NTG Spray

*Respiratory:*
- Albuterol, Atrovent, Epi 1:1000, Narcan (Naloxone), Racemic Epi

*Pain Management (Controlled):*
- Dilaudid, Fentanyl, Ketamine, Morphine

*Sedation (Controlled):*
- Etomidate, Propofol, Versed (Midazolam)

*Other:*
- ASA, Benadryl, Calcium Chloride, D10, Glucagon, Glutose, Haldol, Hydralazine, Ketorolac, Labetalol, Levophed, Lidocaine, Mag Sulfate, Nifedipine, Nitro Drip, Olanzapine, PO Benadryl, Rocuronium, Sodium Bicarb, Tetracaine, TXA Kit, Zofran

**Duplicate Detection:**

MedicLog warns you if you're logging the same medication within 5 minutes:
- Prevents accidental double-documentation
- Critical for multi-provider scenarios
- You can confirm if intentional (e.g., repeat Epi doses)

### 2. Vitals

**Quick Entry with Timers:**

1. Tap **"Pulse"** or **"Respirations"**
2. Countdown timer starts automatically:
   - **Pulse:** 60-second countdown (15-sec with x4 multiplier)
   - **Respirations:** 60-second countdown (30-sec with x2 multiplier)
3. Count as timer runs
4. Tap **"Done"** when complete
5. Value auto-calculated and logged

**Manual Entry:**

1. Tap **"+ Add Entry"** → **"Vitals"**
2. Enter values for:
   - Blood Pressure (systolic/diastolic)
   - Heart Rate (bpm)
   - Respiratory Rate (breaths/min)
   - SpO₂ (percentage)
   - Temperature (°F or °C)
   - Blood Glucose (mg/dL)
3. Add notes if needed
4. Tap **"Save"**

### 3. Procedures

**Quick Access Buttons:**

MedicLog provides quick-tap buttons for common procedures:

- **IV Access:** 16ga, 18ga, 20ga, 22ga, 24ga catheters
- **IO Access:** 15mm, 25mm, 45mm needles
- **Tourniquet:** Auto-starts 15-minute check timer
- **CPR:** Auto-starts 2-minute pulse check timer

**Manual Procedure Entry:**

1. Tap **"+ Add Entry"** → **"Procedure"**
2. Select procedure type
3. Add details (location, size, etc.)
4. Tap **"Save"**

### 4. Cardiac Interventions

**Dedicated Cardiac Button:**

The cardiac button (❤️ icon) provides quick access to:

- **Defibrillation** - Enter joules delivered
- **Cardioversion** - Synchronized shock with joules
- **Pacing** - Settings (rate, mA) and capture status
- **CPR** - Auto-starts pulse check timer

**Usage:**

1. Tap **cardiac button**
2. Select intervention type
3. Enter relevant values (joules, rate, etc.)
4. Tap **"Save"**

---

## Radio Report (MIST Format)

MedicLog automatically generates a **MIST** (Mechanism, Injuries, Signs/Symptoms, Treatment) format radio report for hospital notification.

### Accessing the Radio Report

1. During an active call, tap **"Radio Report"** at the top
2. Review the auto-generated report
3. Use the **Copy** button to copy to clipboard
4. Call receiving facility and deliver report

### MIST Format Structure

**M - Mechanism:**
- How the incident occurred
- *Example:* "50-year-old male, fall from ladder approximately 10 feet"

**I - Injuries:**
- Observed or suspected injuries
- *Example:* "Obvious deformity right wrist, abrasions right elbow"

**S - Signs/Symptoms:**
- Vital signs and patient presentation
- *Example:* "Alert and oriented x4, BP 142/88, HR 96, SpO₂ 98% on room air"

**T - Treatment:**
- Interventions performed
- *Example:* "Right arm splinted, 18ga IV left AC, 2L NS wide open"

### Customizing the Report

The radio report includes:
- ✅ All medications administered (with timestamps)
- ✅ All vital signs taken
- ✅ All procedures performed
- ✅ Chronological timeline

You can edit the generated report directly in the app before calling it in.

---

## Ending a Call

### iPhone

1. Tap **"End Call"** button
2. Review the call summary
3. **Duplicate Detection Check** - If multiple providers logged entries, resolve any flagged duplicates
4. Confirm to complete the call
5. Call is saved to history

### Apple Watch

1. Force-press the screen (or tap menu)
2. Select **"End Call"**
3. Data syncs to iPhone automatically

**Important:** Always verify duplicate entries when working with multiple providers. Duplicate medications could lead to dangerous overdoses if not caught before hospital transfer.

---

## Exporting Data

### Export Options

MedicLog supports multiple export formats:

1. **AirDrop** - Send to iPad, Mac, or another iOS device
2. **Files App** - Save to iCloud Drive or other cloud storage
3. **Email** - Attach to email for ePCR transfer

### How to Export

1. Open a completed call from **History**
2. Tap **"Export"** button
3. Choose format:
   - **PDF** - Formatted call report
   - **CSV** - Spreadsheet data
   - **JSON** - Raw structured data
4. Select destination (AirDrop, Files, Email)

### What's Included in Exports

- Complete call timeline with timestamps
- All medications, doses, routes
- All vital signs
- All procedures performed
- User/provider attribution
- Device attribution (iPhone/Apple Watch)
- Run number and call duration

---

## Settings

### User Information

**User ID:** Your agency identification number
- Used for provider attribution on all entries
- Format: Agency-specific (e.g., "A123", "P-456")

**User Name:** Your full name
- Displayed on call logs and exports
- Used when User ID is not configured

**Unit Number:** Your ambulance/vehicle designation
- Fallback identification if User ID not set
- Format: Agency-specific (e.g., "M-12", "E-3")

### App Settings

**Default Route:** Pre-select your preferred medication route
- Options: IV, IM, IO, PO, SL, IN, ET, Nebulized, SQ
- Can be overridden per medication

**Certification Level:** Filter medications by scope of practice
- **Coming in Phase 2** - Currently all medications visible
- Will filter formulary based on EMT-B, AEMT, Paramedic, or custom certifications

**Medication Timers:** Enable/disable automatic countdown timers
- Toggles for individual medications
- Customize timer durations per agency protocols

### Privacy & Data

**Local Storage:** All data stored encrypted on device
- No cloud sync in beta version
- HIPAA considerations: Use at your own discretion
- Future versions will include full HIPAA compliance features

**Data Retention:** Calls stored indefinitely until manually deleted
- Export calls before deleting
- No automatic backup in beta

---

## Apple Watch Features

### Current Capabilities (v0.9β)

**✅ Working:**
- Call start/end sync with iPhone
- Entry logging (manual tap entry)
- View recent entries (last 3)
- Real-time sync with iPhone
- Connectivity indicator (green = connected)
- Emergency "Start Anyway" for offline mode

**⚠️ Limited:**
- Voice input not functional in this beta
- Manual entry only (tap keyboard/scribble)

**🔜 Coming in Phase 2:**
- Full voice recognition for hands-free logging
- Complete entry editing
- Improved sync reliability

### Watch Workflow

1. **Start call** on watch or phone (syncs automatically)
2. **Add entries** using:
   - Quick medication buttons
   - Manual entry screen
   - Vitals/procedures buttons
3. **Monitor sync** - Green indicator shows connection
4. **End call** - Data syncs to phone for export

### Offline Mode

If iPhone is unavailable:
1. Watch prompts **"Start Anyway"**
2. Log entries locally on watch
3. Data syncs when reconnected
4. Merge conflicts resolved automatically

**Note:** For best reliability in this beta, use iPhone as primary device with watch as backup.

---

## Tips for Field Use

### Glove-Friendly Operation

- **Large touch targets** - All buttons sized for gloved fingers
- **Minimal typing** - Quick-tap buttons for common actions
- **Smart defaults** - Pre-filled doses/routes reduce taps
- **Voice input (Phase 2)** - Hands-free logging coming soon

### Best Practices

**1. Start calls immediately when dispatched**
- Paste run number from dispatch text message
- MedicLog auto-extracts the E# format

**2. Log interventions in real-time**
- Don't wait until transport
- Timestamps are critical for medication administration
- Reduces documentation errors

**3. Use quick-tap buttons**
- Faster than manual entry
- Pre-configured for common scenarios
- Confirm defaults match your protocols

**4. Check for duplicates at call end**
- Critical when multiple providers are working
- Resolve before hospital handoff
- Prevents dangerous medication errors

**5. Export calls promptly**
- AirDrop to iPad for ePCR entry
- Email to agency documentation system
- Don't rely on device storage long-term

### Moving Vehicle Use

**Recommendations:**
- Use landscape orientation for stability
- Brace phone/hand against surface
- Quick-tap buttons reduce missed taps
- Consider watch for basic logging during transport

### Multi-Provider Scenarios

When working with partners:
1. Each provider logs their own interventions
2. Different User IDs identify who did what
3. Duplicate detection flags same med/dose/time
4. Resolve duplicates together before hospital handoff

### Battery Management

- Extended runtime on watch uses more battery
- Consider bringing backup power bank
- Close other apps before calls
- Watch works offline if phone dies

---

## Getting Help

**Bug Reports:** [GitHub Issues](https://github.com/MedicLog/mediclog-support/issues)  
**Feature Requests:** [GitHub Issues](https://github.com/MedicLog/mediclog-support/issues)  
**Support Email:** mediclog2026@gmail.com  
**Privacy Policy:** [View Policy](https://gist.githubusercontent.com/jj33/c66587bc809865cbcc136ea6cb9e0481/raw/18cff1eaef645fd539947a737f1a46f36633080b/MedicLog-Privacy-Policy.md)

---

**MedicLog v0.9β** - Built for EMS, by EMS 🚑

*This is beta software under active development. Thank you for your feedback!*
