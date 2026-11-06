# В.6 Системна інструкція і початок запитань анкети для методу аналітичних мереж (керівник експлуатації на об'єктах, розділ 3, друге опитування групи GPT-5.6)

Системна інструкція:

```text
You are a virtual expert in a structured judgment study. Role: Field operations manager. You manage technicians, work permits and maintenance windows at field sites. You weigh the operational friction that a control creates (criterion U).
```

Нижче наведено початок запитань анкети. Після нього запитання охоплюють решту 367 пар, 35 часток усунених втрат і 5 оцінок очікуваних річних втрат, а для двох останніх частин наведено також заголовки й перші пункти.

```text
You are taking part in a structured expert elicitation for the Analytic Network Process (ANP). Answer as the expert described in your instructions, from that expert's own professional experience and priorities.

Decision problem: Prioritize security controls for a national critical infrastructure operator that must allocate limited resources, under realistic budget and staffing constraints, to reduce mission risk over the next 12-18 months against sophisticated external state adversaries.

The network has four groups of elements.

Security controls:
- MON: ICS network monitoring and anomaly detection
- SEG: Network segmentation and unidirectional gateways
- IDM: Identity, MFA and privileged access management
- IR: Incident response and staff training
- SUP: Supply-chain security, including SBOM and code signing
- BAK: Offline immutable backups and recovery for ICS
- PHY: Physical and environmental hardening of sites

Evaluation criteria:
- E: Effectiveness against the TTPs of state actors
- T: Time to implement (less is better)
- U: Operational impact and availability friction (less is better)
- C: Implementation cost (less is better)
- P: Policy and compliance fit (NIST CSF 2.0, NIS2)

Threat vectors:
- PHISH: Targeted spear-phishing
- SC: Supply-chain compromise
- EXP: Remote exploitation of vulnerabilities
- INS: Insider threat
- SAB: Physical sabotage

Implementation constraints:
- BUD: Budget limits
- WRK: Workforce readiness
- LOCK: Vendor lock-in risk

For every numbered pair below, state which element is preferred ('first', 'second' or 'equal') and the intensity of the preference. Use Saaty's 1-9 scale: 1 = equal, 3 = moderately more, 5 = strongly more, 7 = very strongly more, 9 = extremely more; 2, 4, 6 and 8 are intermediate values. Use intensity 1 only with 'equal'. Do not search the web, read files or run commands. Return one entry for every pair, one share for every coverage item and one value for every loss item, and nothing else, as the JSON object required by the output schema.

Under constraint LOCK (Vendor lock-in risk), which control is easier to implement?
Q001: first = SEG (Network segmentation and unidirectional gateways); second = PHY (Physical and environmental hardening of sites)
Q002: first = MON (ICS network monitoring and anomaly detection); second = IDM (Identity, MFA and privileged access management)
Q003: first = SUP (Supply-chain security, including SBOM and code signing); second = SEG (Network segmentation and unidirectional gateways)
…
Coverage. For each control and threat vector below, estimate the share of the expected annual loss from that threat that the control alone would remove at this operator, as a number from 0 to 1.
V01: control MON (ICS network monitoring and anomaly detection) against threat PHISH (Targeted spear-phishing)
…
Expected annual loss. Estimate the expected annual loss, in million US dollars, that each threat vector would cause this operator if none of the seven controls above were added.
L1: PHISH (Targeted spear-phishing)
…
```
