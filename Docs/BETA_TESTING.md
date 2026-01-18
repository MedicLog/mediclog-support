# MedicLog Beta Testing Guide

**Version:** 0.9β  
**TestFlight Program**  
**Last Updated:** January 18, 2026

---

## Welcome Beta Testers!

Thank you for helping test MedicLog. Your feedback is invaluable in building a reliable EMS logging tool. This guide explains what to test, known issues, and how to provide effective feedback.

---

## What is Beta Testing?

Beta testing means:
- **You're using pre-release software** - Expect bugs and missing features
- **Your feedback shapes development** - Report what works and what doesn't
- **Features will change** - Updates may break or improve functionality
- **No guarantees** - This is NOT production-ready software

**Important:** Do not rely on MedicLog as your only documentation system during beta. Always use your agency's official ePCR as primary documentation.

---

## TestFlight Installation

### Initial Setup

1. Install **TestFlight** from the App Store
2. Accept the beta invitation email from MedicLog
3. Open TestFlight and tap **"Install"** next to MedicLog
4. Launch MedicLog from your home screen

### Getting Updates

TestFlight automatically notifies you when updates are available:
- Tap the notification to install
- Or open TestFlight → MedicLog → **"Update"**

**Note:** Beta builds expire after 90 days. TestFlight will prompt you to install a new build before expiration.

---

## What to Test

### High Priority Testing

These features are critical and need the most testing:

**1. Call Lifecycle**
- Start a call with run number
- Log multiple entries (medications, vitals, procedures)
- End call and verify duplicate detection
- Export call to PDF/CSV

**2. Medication Logging**
- Use quick-tap medication buttons
- Verify default doses and routes
- Test medication timers
- Try logging the same medication twice (duplicate detection)

**3. Vitals Entry**
- Use pulse/respirations countdown timers
- Manual vitals entry
- Verify calculations and timestamps

**4. Radio Report**
- Generate MIST format report
- Copy to clipboard
- Verify all entries included

**5. Data Export**
- AirDrop to another device
- Save to Files app
- Email export
- Verify PDF formatting

### Medium Priority Testing

Features that work but need validation:

**1. Multi-Device Sync (iPhone + Watch)**
- Start call on one device, view on other
- Add entries from both devices
- Verify sync happens in real-time
- Test offline mode ("Start Anyway" on watch)

**2. Medication Timers**
- Verify countdown timers appear
- Test notification alerts
- Check timer accuracy

**3. Settings**
- Change User ID, Name, Unit Number
- Verify attribution on logged entries
- Test different default routes

**4. User Interface**
- Test with gloves in field conditions
- Verify buttons are large enough
- Check readability in sunlight
- Test in moving vehicle

### Low Priority (Known Issues)

These features are known to be broken or limited:

**1. Voice Input** - Not working in v0.9β
- Watch voice input disabled
- iPhone uses keyboard dictation only
- Will be rebuilt in Phase 2

**2. Entry Editing** - Not implemented yet
- Cannot edit entries after creation
- Coming in Phase 2

---

## Known Issues

Before reporting a bug, check if it's already known:

### Critical Issues

**⚠️ Watch voice input not working**
- Voice recognition fails on Apple Watch
- Manual entry (keyboard/scribble) works
- High priority for Phase 2

**⚠️ Cannot edit entries**
- No edit functionality in v0.9β
- Must delete entire call to fix errors
- Editing with audit trail coming in Phase 2

### Minor Issues

**Assets warning on first launch**
- Cosmetic warning about missing asset sizes
- Does not affect functionality
- Will be resolved before public release

**Connectivity indicator may show green when iPhone app closed**
- Heartbeat system should detect within ~5 seconds
- If persistent, report as bug

**Sync delays**
- 1-2 second delay between devices is normal
- If >5 seconds, check connectivity indicator
- Report if persistent

---

## How to Report Bugs

### Before Reporting

1. **Check Known Issues** (above) - Don't report if already known
2. **Try to reproduce** - Can you make it happen again?
3. **Restart the app** - Does it still happen?

### What to Include in Bug Reports

**Required information:**
- **Device model** - (e.g., iPhone 14 Pro, Apple Watch Series 9)
- **iOS/watchOS version** - Settings → General → About
- **MedicLog version** - Shown in Settings
- **Steps to reproduce** - What did you do before the bug happened?
- **Expected behavior** - What should have happened?
- **Actual behavior** - What actually happened?

**Helpful additions:**
- Screenshots or screen recordings
- Console logs (if technically inclined)
- Whether it happens every time or randomly

### Where to Report

**GitHub Issues (Preferred):**  
[https://github.com/MedicLog/mediclog-support/issues](https://github.com/MedicLog/mediclog-support/issues)

1. Click **"New Issue"**
2. Choose **"Bug Report"** template
3. Fill in all sections
4. Submit

**Email (Alternative):**  
mediclog2026@gmail.com

Subject: "MedicLog Bug Report - [Brief Description]"

### Bug Report Examples

**Good Bug Report:**
```
Title: App crashes when exporting calls with >50 entries

Device: iPhone 14 Pro, iOS 18.2
MedicLog Version: 0.9β (build 3)

Steps to reproduce:
1. Create call with 50+ medication entries
2. Tap "Export" button
3. Select "PDF" format
4. App crashes immediately

Expected: PDF should generate and share sheet appear
Actual: App force-quits with no error message

Reproducible: Yes, every time with >50 entries
Works fine with <30 entries

[Screenshot attached]
```

**Bad Bug Report:**
```
Title: Export doesn't work

The export button doesn't work. Please fix.
```

---

## How to Request Features

### What Makes a Good Feature Request?

**Include:**
- **Problem description** - What workflow is painful?
- **Proposed solution** - How would the feature work?
- **Use case** - When would you use this?
- **Priority** - Critical for your work or nice-to-have?

**Example:**
```
Title: Add Glasgow Coma Scale (GCS) quick entry

Problem: Entering GCS requires opening vitals screen and typing three numbers. 
Takes too long in critical situations.

Proposed solution: Dedicated GCS button with eye/verbal/motor sliders or 
quick-tap buttons for common scores (3, 8, 15).

Use case: Trauma and altered mental status calls. Used on most critical patients.
Need to document quickly and repeatedly.

Priority: High - GCS is required documentation for trauma patients
```

### Where to Submit

**GitHub Issues:**  
[https://github.com/MedicLog/mediclog-support/issues](https://github.com/MedicLog/mediclog-support/issues)

1. Click **"New Issue"**
2. Choose **"Feature Request"** template
3. Describe the feature
4. Submit

---

## Real-World Testing Scenarios

### Scenario 1: Cardiac Arrest

**Setup:** Simulate a cardiac arrest call

**Test:**
1. Start call with run number
2. Log CPR start (verify 2-min timer appears)
3. Log Epinephrine 1:10,000 1mg IV (verify 4-min timer)
4. Wait for timer, log second Epi dose
5. Log defibrillation 200J
6. Take vitals set
7. End call, verify all entries timestamped correctly
8. Generate Radio Report, verify MIST format
9. Export to PDF

**What to look for:**
- Timers appearing and counting down
- Duplicate detection when logging second Epi
- All entries in chronological order
- Export includes all data

### Scenario 2: Multi-Provider Call

**Setup:** Simulate two medics working together (requires 2 devices)

**Test:**
1. **Device A:** Start call, enter run number
2. **Device B:** Open app, verify call syncs
3. **Device A:** Log Fentanyl 50mcg IV (User A)
4. **Device B:** Log Versed 2mg IV (User B)
5. **Device B:** Accidentally log same Fentanyl dose
6. End call on either device
7. Resolve duplicate detection warning
8. Export from both devices, verify consistency

**What to look for:**
- Both devices show all entries
- User attribution correct (Device A vs Device B)
- Duplicate detection flags identical medications
- Sync happens within 1-2 seconds

### Scenario 3: Field Conditions Test

**Setup:** Use in realistic field environment

**Test:**
1. Wear work gloves (latex, nitrile, or structural)
2. Simulate moving vehicle (have someone drive you)
3. Test in direct sunlight
4. Try logging while standing/walking

**What to look for:**
- Can you tap buttons accurately with gloves?
- Are buttons large enough?
- Screen readable in sunlight?
- Any accidental taps in moving vehicle?

### Scenario 4: Watch-Only Operation

**Setup:** Test watch independence

**Test:**
1. Turn off iPhone Bluetooth or move out of range
2. Start call on watch ("Start Anyway" mode)
3. Log several entries manually
4. Reconnect to iPhone
5. Verify all entries synced

**What to look for:**
- Watch allows offline operation
- Entries persist during disconnection
- Sync happens automatically on reconnection
- No data loss

---

## Feedback We Value Most

### Critical Feedback

**Safety Issues:**
- Wrong medication routes allowed
- Duplicate detection not working
- Data loss or corruption
- Sync failures causing missing entries

**Workflow Blockers:**
- Cannot complete essential tasks
- Takes too many taps for common actions
- Unusable with gloves
- Too slow for field use

### Helpful Feedback

**Usability Issues:**
- Confusing interfaces
- Unclear button labels
- Difficult to read text
- Navigation problems

**Feature Gaps:**
- Common medications missing from formulary
- Protocol-specific needs
- Integration with existing workflows
- Export format requirements

### Nice-to-Have Feedback

**Preferences:**
- Color scheme preferences
- Icon design opinions
- Layout suggestions
- Feature priority opinions

---

## Beta Tester Expectations

### What We Ask of You

**Testing:**
- Use MedicLog during real or simulated calls
- Try all major features at least once
- Test in realistic field conditions (if safe to do so)
- Try to break things (edge cases, unusual inputs)

**Reporting:**
- Report bugs with complete information
- Submit feature requests with clear use cases
- Respond to follow-up questions on GitHub Issues
- Test fixes in updated builds

**Communication:**
- Be honest about what works and what doesn't
- Share your EMS experience and workflow needs
- Suggest improvements based on field use
- Be patient - this is beta software

### What You Can Expect

**From the Developer:**
- Regular updates (aim for weekly during active development)
- Responses to bug reports within 48 hours
- Consideration of all feature requests
- Transparency about development priorities

**From the App:**
- Bugs and crashes (it's beta!)
- Missing features
- Changes that might break your workflow
- Improvements based on your feedback

### What Beta Testing Is NOT

**❌ Not a free app trial** - This is pre-release testing, not a demo  
**❌ Not a substitute for official ePCR** - Do not rely on this as primary documentation  
**❌ Not guaranteed feature implementation** - Requests may not be built  
**❌ Not production-ready** - Do not use in life-critical situations without backup

---

## Testing Checklist

Use this checklist to ensure comprehensive testing:

### Core Features
- [ ] Install via TestFlight
- [ ] Configure User ID, Name, Unit Number
- [ ] Start a call with run number
- [ ] Add medication entry (quick button)
- [ ] Add vitals entry (with timer)
- [ ] Add procedure entry
- [ ] View Radio Report (MIST)
- [ ] End call
- [ ] Resolve duplicate detection
- [ ] Export call (PDF)
- [ ] Export call (CSV)

### Apple Watch Features
- [ ] Install on Apple Watch
- [ ] Start call from watch
- [ ] Add entry from watch (manual)
- [ ] View recent entries on watch
- [ ] Verify sync with iPhone
- [ ] Test offline mode ("Start Anyway")
- [ ] Test reconnection after offline

### Field Conditions
- [ ] Test with gloves (latex/nitrile)
- [ ] Test in moving vehicle
- [ ] Test in direct sunlight
- [ ] Test with cold/numb fingers

### Multi-Device
- [ ] Sync between iPhone and watch
- [ ] Test with multiple providers (if possible)
- [ ] Verify user attribution
- [ ] Test duplicate detection

### Edge Cases
- [ ] Very long call (>50 entries)
- [ ] Rapid entry logging
- [ ] Force-quit app during call
- [ ] Low battery scenarios
- [ ] Airplane mode
- [ ] Background app usage

---

## Resources

**Documentation:**
- [User Guide](USER_GUIDE.md) - Complete feature documentation
- [Medication Reference](MEDICATION_REFERENCE.md) - Full formulary list
- [FAQ](FAQ.md) - Common questions answered

**Support:**
- **Bug Reports:** [GitHub Issues](https://github.com/MedicLog/mediclog-support/issues)
- **Feature Requests:** [GitHub Issues](https://github.com/MedicLog/mediclog-support/issues)
- **Email:** mediclog2026@gmail.com

**Community:**
- **GitHub:** [MedicLog Organization](https://github.com/MedicLog)
- **TestFlight:** Check for updates regularly

---

## Thank You!

Your participation in beta testing helps build a better EMS logging tool for everyone. Every bug report, feature request, and piece of feedback makes MedicLog more useful for paramedics and EMTs in the field.

**Questions?** Email mediclog2026@gmail.com or open a GitHub Issue.

---

*Last Updated: January 18, 2026*  
*MedicLog v0.9β - Built for EMS, by EMS* 🚑

**Remember:** This is beta software. Always maintain official documentation through your agency's ePCR system.
