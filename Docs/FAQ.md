# MedicLog Frequently Asked Questions (FAQ)

**Version:** 0.9β  
**Last Updated:** January 18, 2026

---

## Table of Contents

- [General Questions](#general-questions)
- [Features & Functionality](#features--functionality)
- [Apple Watch](#apple-watch)
- [Data & Privacy](#data--privacy)
- [Troubleshooting](#troubleshooting)
- [Future Development](#future-development)

---

## General Questions

### What is MedicLog?

MedicLog is a professional EMS call logging application for iPhone, iPad, Apple Watch, and Mac. It's designed for paramedics and EMTs to document medical interventions during emergency calls using glove-friendly, voice-first interfaces optimized for moving ambulances.

### Who can use MedicLog?

MedicLog is designed for:
- EMTs (Basic, Advanced, Paramedic)
- Critical care transport teams
- Flight paramedics
- Wilderness medicine providers
- Any EMS provider who needs to document interventions

The app is currently in TestFlight beta testing.

### Is MedicLog free?

During the TestFlight beta phase, MedicLog is free to use. Future pricing plans have not been determined. Beta testers will receive advance notice of any pricing changes.

### What platforms are supported?

- **iPhone:** iOS 18.0 or later (primary platform)
- **iPad:** iPadOS 18.0 or later
- **Mac:** macOS 14.0 or later (Apple Silicon)
- **Apple Watch:** watchOS 10.0 or later

---

## Features & Functionality

### Can I edit entries after I log them?

**Not in v0.9β.** Entry editing with full audit trail is planned for Phase 2 (post-TestFlight). Currently, if you make an error, you'll need to:
1. Add a correcting entry with notes (e.g., "Previous Versed dose was 2mg, not 4mg")
2. Delete the entire call and re-enter (not recommended for active calls)

### Why can't I use voice input?

Voice input is **limited in v0.9β**:
- **Apple Watch:** Voice recognition not functional (manual entry only)
- **iPhone:** Uses keyboard dictation (not ideal for field use)

Full voice recognition with hands-free logging is coming in Phase 2. This is a high-priority feature.

### How does duplicate detection work?

MedicLog flags potential duplicate medications when:
- Same medication name
- Same dose and route
- Logged within 5 minutes
- Especially important when multiple providers are logging

You're prompted to resolve duplicates at call completion to prevent dangerous documentation errors.

### What is the Radio Report (MIST) feature?

MedicLog auto-generates a structured hospital notification report in MIST format:
- **M**echanism - How incident occurred
- **I**njuries - Observed/suspected injuries
- **S**igns/Symptoms - Vitals and presentation
- **T**reatment - Interventions performed

You can copy the report to clipboard and deliver it via radio or phone to the receiving facility.

### Can I customize the medication list?

**Not yet.** Custom formulary import is planned for Phase 3. The current 37-medication list represents common EMS medications across various protocols.

To request additional medications, submit a feature request on [GitHub Issues](https://github.com/MedicLog/mediclog-support/issues).

### How do medication timers work?

Some medications automatically start countdown timers when logged:
- **Epinephrine (IV):** 4-minute timer for next dose
- **Fentanyl/Versed:** 10-minute reassessment timer
- **Albuterol:** 5-minute treatment timer

These are **organizational preferences** based on common re-dosing intervals - **not clinical recommendations**. Always follow your protocols.

### Can MedicLog calculate medication doses?

**Not in v0.9β.** Weight-based dose calculators are planned for future versions. Currently, you must calculate doses manually and enter the calculated amount.

---

## Apple Watch

### Does the Apple Watch app work?

**Partially.** In v0.9β:
- ✅ Call start/end sync
- ✅ Manual entry logging
- ✅ View recent entries
- ✅ Connectivity indicator
- ⚠️ Voice input NOT working
- ⚠️ Limited functionality

The watch works best as a **backup device** in this beta. Use iPhone as primary.

### Why isn't Watch voice input working?

This is a known issue in v0.9β. The voice recognition system needs to be rebuilt using proper AVFoundation framework. This is prioritized for Phase 2.

### Do I need my iPhone nearby to use the watch app?

**For best experience, yes.** However:
- Watch can start calls independently ("Start Anyway" mode)
- Entries logged offline sync when reconnected
- Some features require iPhone connection

### Will the watch work without cellular?

Yes, as long as it's connected to your iPhone via Bluetooth. Cellular is not required for MedicLog.

---

## Data & Privacy

### Where is my data stored?

All data is **stored locally on your device** with encryption. MedicLog does not:
- Upload data to cloud servers
- Sync via iCloud
- Transmit data over the internet (except for TestFlight crash reports)

Your call logs remain on your iPhone/iPad/Mac until you manually export or delete them.

### Is MedicLog HIPAA compliant?

**Not yet.** HIPAA compliance features are planned for Phase 3, including:
- File encryption at rest
- Audit trails
- Access controls
- Business Associate Agreement (BAA) support

**Current recommendation:** Treat MedicLog as a **field logging tool** for immediate documentation. Transfer data to your agency's official ePCR system for HIPAA-compliant storage.

### Can I sync data between my iPhone and iPad?

**Not in v0.9β.** iCloud sync is not implemented. Each device stores its own call history independently.

To transfer calls between devices:
1. Export call from iPhone (AirDrop, Files, Email)
2. Import on iPad (future feature)

### What happens if I lose my phone?

**Data is lost** unless you've exported calls. MedicLog does not back up data to cloud services.

**Best practices:**
- Export calls promptly after completion
- AirDrop to iPad or Mac for redundancy
- Email exports to agency documentation system
- Don't rely on device storage long-term

### Does MedicLog collect analytics or usage data?

TestFlight may collect crash reports and basic usage analytics to improve app stability. No patient data or personal information is included in these reports.

See the [Privacy Policy](https://gist.githubusercontent.com/jj33/c66587bc809865cbcc136ea6cb9e0481/raw/18cff1eaef645fd539947a737f1a46f36633080b/MedicLog-Privacy-Policy.md) for complete details.

### Can I use MedicLog for actual patient care documentation?

MedicLog is designed as a **field logging tool** to capture interventions in real-time. However:

**✅ Appropriate use:**
- Real-time documentation during active calls
- Backup documentation when ePCR is unavailable
- Training and simulation scenarios
- Personal skill tracking

**❌ Not a replacement for:**
- Official ePCR systems
- Agency-required documentation
- Legal patient care records (until HIPAA compliance implemented)
- Billing/reimbursement documentation

Always transfer MedicLog data to your agency's official ePCR system for permanent records.

---

## Troubleshooting

### The app crashes when I try to start a call

Try these steps:
1. Force-quit the app (swipe up in App Switcher)
2. Restart your iPhone
3. Verify you're running iOS 18.0 or later
4. Delete and reinstall MedicLog from TestFlight

If the issue persists, report it via [GitHub Issues](https://github.com/MedicLog/mediclog-support/issues) with:
- Device model
- iOS version
- Steps to reproduce

### My watch won't connect to the iPhone app

Check these items:
1. Both devices on same Wi-Fi or Bluetooth connected
2. MedicLog installed on both devices
3. Watch is unlocked and on wrist
4. iPhone's Bluetooth is enabled
5. Try restarting both devices

The connectivity indicator (green dot) shows real-time connection status.

### Medication timers aren't working

Timers require:
- ✅ Medication has timer enabled (not all medications have timers)
- ✅ Entry successfully logged
- ✅ App running in background

If timers stop:
- Check if app was force-quit
- Verify notification permissions enabled
- Report persistent issues on GitHub

### I can't export my call logs

Export issues are often related to:
1. **No destination selected** - Choose AirDrop, Files, or Email
2. **AirDrop visibility** - Ensure receiving device has AirDrop enabled
3. **Storage full** - Check device storage
4. **PDF generation failure** - Try CSV export instead

If all formats fail, report the bug with your device details.

### The app is running slowly

Performance issues may indicate:
- Low device storage
- iOS needs update
- Too many background apps running
- Corrupted app cache

Try:
1. Close other apps
2. Restart device
3. Delete and reinstall MedicLog
4. Ensure iOS 18.0+ installed

### How do I report a bug?

**Best method:** [GitHub Issues](https://github.com/MedicLog/mediclog-support/issues)

Include:
- Device model and iOS version
- Steps to reproduce the issue
- Expected vs actual behavior
- Screenshots if applicable

**Alternative:** Email mediclog2026@gmail.com

---

## Future Development

### When will voice input be fixed?

Voice recognition is the **top priority for Phase 2** (post-TestFlight). We're rebuilding the voice system using AVFoundation for reliable hands-free logging.

Target: Q1 2026 (early 2026)

### When can I edit entries?

Entry editing with audit trails is planned for **Phase 2**. This ensures you can correct errors while maintaining a complete record of changes (required for legal documentation).

Target: Q1 2026

### Will there be a web version?

No plans for a web version. MedicLog is designed specifically for mobile/wearable platforms optimized for field use. Web-based ePCR systems already exist for office documentation.

### Can I customize the medication formulary?

Custom formulary import is planned for **Phase 3** (Agency Distribution). This will allow:
- Agency-specific protocols
- Custom medication lists
- Certification-level filtering
- Protocol decision trees

Target: Mid-2026

### Will MedicLog integrate with my ePCR system?

ePCR integration is not currently planned. However, MedicLog supports:
- PDF export (for attachment to ePCR)
- CSV export (for data import)
- JSON export (for custom integrations)

If you have specific integration needs, submit a feature request on GitHub.

### What about HIPAA compliance?

Full HIPAA compliance features are planned for **Phase 3**:
- File encryption at rest
- Access controls and authentication
- Audit trails
- Business Associate Agreements (BAA)
- Secure data transmission

Target: Mid-2026

Until HIPAA compliance is implemented, use MedicLog for field logging only and transfer to official systems.

### Can I suggest new features?

**Yes!** Feature requests are welcome via [GitHub Issues](https://github.com/MedicLog/mediclog-support/issues).

When requesting features, include:
- Clear description of the feature
- Use case / problem it solves
- Whether it's critical for your workflow
- Whether other EMS systems have this feature

### What's the roadmap?

**Phase 1 (Current - v0.9β):**
- TestFlight beta testing
- Basic medication/vitals/procedure logging
- Radio Report (MIST)
- Export functionality

**Phase 2 (Q1 2026 - v1.0):**
- Entry editing with audit trail
- Voice input restoration
- Watch sync improvements
- UX refinements

**Phase 3 (Mid-2026 - v1.1+):**
- Custom formulary import
- HIPAA compliance features
- Multi-agency distribution
- Advanced certification filtering

---

## Contact & Support

### How do I get help?

**Bug Reports & Feature Requests:**  
[GitHub Issues](https://github.com/MedicLog/mediclog-support/issues)

**General Support:**  
mediclog2026@gmail.com

**Documentation:**
- [User Guide](USER_GUIDE.md)
- [Medication Reference](MEDICATION_REFERENCE.md)
- [Privacy Policy](https://gist.githubusercontent.com/jj33/c66587bc809865cbcc136ea6cb9e0481/raw/18cff1eaef645fd539947a737f1a46f36633080b/MedicLog-Privacy-Policy.md)

### Can I contribute to development?

MedicLog is proprietary software - source code is not open source. However, you can contribute through:
- **Beta testing** - Test new features and report issues
- **Feature suggestions** - Submit ideas via GitHub Issues
- **Documentation** - Help improve user guides
- **Feedback** - Share your field experience

### How do I stay updated on new releases?

- TestFlight automatically notifies you of updates
- Follow GitHub Issues for feature discussions
- Email updates for major releases

### Who develops MedicLog?

MedicLog is developed by **Joel Jameson**, an EMT and paramedic student, with real-world EMS experience informing every design decision.

**Organization:** [MedicLog on GitHub](https://github.com/MedicLog)

---

## Still Have Questions?

**Didn't find your answer?** 

- Check the [User Guide](USER_GUIDE.md) for detailed instructions
- Search [GitHub Issues](https://github.com/MedicLog/mediclog-support/issues) to see if it's already been asked
- Submit a new issue if your question isn't answered
- Email mediclog2026@gmail.com for private inquiries

---

*Last Updated: January 18, 2026*  
*MedicLog v0.9β - Built for EMS, by EMS* 🚑
