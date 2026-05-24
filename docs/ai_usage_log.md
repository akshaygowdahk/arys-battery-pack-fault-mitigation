# AI Usage Log

**Candidate:** Akshay Gowda HK | USN: 1BM22EE007  
**Assignment:** Q3 – 10s10p Battery Pack Fault & Mitigation (21700 NMC)

---

## Tool: Claude (Anthropic) — claude.ai

### Session 1 – Model Review & Parameter Validation
**Prompt used:**
> "I am working on Q3 of section A, are you capable of checking a simulink file and analyse the work done till now?"

**How output was used:**
- Validated Molicel INR-21700-P45B cell parameters (capacity, internal resistance, thermal mass)
- Identified cell naming inconsistency between P25B and P45B — corrected to P45B
- Confirmed 10s10p Battery Builder configuration was correctly set up
- Reviewed Simulink model architecture: SOH estimator, discharge loop, fault injection logic

**Adaptations made:**
- Adjusted report to consistently reference P45B cell
- Used Claude's pack-level spec calculations (36V nominal, 45Ah, 1.62kWh) in documentation

### Session 2 – Documentation & GitHub Setup
**Prompt used:**
> "I have finished the model as much as possible, I need help with submission"
> "start building the repo, we'll do report later"

**How output was used:**
- GitHub repository structure generated
- README.md drafted with full project scope, cell specs, simulation overview, tools, and run instructions
- `.gitignore` and folder placeholders created for incremental commits

**Adaptations made:**
- Folder structure customised to match actual simulation files
- Submission email details filled in from assignment PDF
