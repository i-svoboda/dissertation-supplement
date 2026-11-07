# 11. Початок запитань анкети для вибору засобів захисту оператора системи розподілу (інженер АСУ ТП, перше формулювання, розділ 5, перший запуск)

Запитання кожної анкети надсилалися моделі одним запитом. Нижче наведено інструкцію та перший блок запитань (порівняння засобів захисту щодо варіанта ВС), які отримав віртуальний експерт у ролі інженера АСУ ТП (перше формулювання, перший запуск). Далі анкета містить ще 32 блоки парних порівнянь, зокрема порівняння груп елементів мережі, а також блок часток усунених втрат (35 оцінок) і блок очікуваних річних втрат (5 оцінок). Усього в анкеті 376 парних порівнянь. Опис модельного прикладу і варіантів сценаріїв такий самий, як у матеріалі 10, крім порядку варіантів, тому в тексті інструкції його не наведено. Кожна анкета має власний порядок варіантів в описі, блоків парних порівнянь, пар у блоках, елементів у парах і оцінок у блоках часток усунених втрат та очікуваних втрат, який задає початкове значення генератора псевдовипадкових чисел цієї анкети. Друге і третє формулювання відрізняються від першого лише вступом і запитаннями до блоків. Відповідь подається одним об'єктом JSON з чотирма масивами: парні порівняння (Q001–Q376), частки усунених втрат (V01–V35), очікувані річні втрати (L1–L5) та обґрунтування блоків (B01–B35).

```text
You are taking part in a structured expert elicitation for the Analytic Network Process (ANP). Answer as the expert described below, from that expert's own professional experience and priorities.

Expert: ICS engineer. You operate PLC and DCS equipment from several vendors at a critical infrastructure operator. Safety and availability come first for you, and you distrust intrusive scanning of live control systems. Other things being equal, less implementation time, cost and operational impact is better.
This expert profile was written for choosing security controls. Use the same professional experience and viewpoint to judge the controls, criteria, scenario variants and constraints defined below for the regional electricity distribution operator described here.

Decision problem: Prioritize security controls for the regional electricity distribution operator described below, which must allocate limited resources, under realistic budget and staffing constraints, to reduce mission risk over the next 12-18 months against sophisticated external state adversaries.

[опис організації, початкового стану A, цільового інциденту B, звітів про інциденти та варіантів сценаріїв – як у матеріалі 10, варіанти в порядку EE, RS, PC, DS, MP; не наведено]

All variants end in the same target incident, so their consequences are the same.

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

Scenario variants:
- EE: Enterprise endpoint compromise
- RS: Remote service compromise
- PC: Personnel credential compromise
- DS: Dispatcher session takeover
- MP: Maintenance provider credential compromise

Implementation constraints:
- BUD: Budget limits
- WRK: Workforce readiness
- LOCK: Vendor lock-in risk

How to answer. Each block below asks one question. For every numbered pair, state which element is preferred ('first', 'second' or 'equal') and the intensity of the preference; the preferred element is the one that the question of the block favours. Use Saaty's 1-9 scale: 1 = equal, 3 = moderately more, 5 = strongly more, 7 = very strongly more, 9 = extremely more; 2, 4, 6 and 8 are intermediate values. Use intensity 1 only with 'equal'. For every coverage item, give a share as a number from 0 to 1. For every loss item, give an amount in million US dollars. Judge each item on its merits; do not compute the matrices or check them for consistency. For every block, give one short justification of one or two sentences at the level of the descriptions above, without device commands, exploit details or other technical attack instructions. Do not search the web, read files or run commands. Return one entry for every pair, every coverage item, every loss item and every block, and nothing else, as the JSON object required by the output schema.

Block B01. With respect to scenario variant RS (Remote service compromise), which control reduces this risk more?
Q001: first = SEG (Network segmentation and unidirectional gateways); second = MON (ICS network monitoring and anomaly detection)
Q002: first = BAK (Offline immutable backups and recovery for ICS); second = MON (ICS network monitoring and anomaly detection)
Q003: first = SUP (Supply-chain security, including SBOM and code signing); second = PHY (Physical and environmental hardening of sites)
Q004: first = BAK (Offline immutable backups and recovery for ICS); second = IDM (Identity, MFA and privileged access management)
Q005: first = SUP (Supply-chain security, including SBOM and code signing); second = IR (Incident response and staff training)
Q006: first = IR (Incident response and staff training); second = PHY (Physical and environmental hardening of sites)
Q007: first = MON (ICS network monitoring and anomaly detection); second = SUP (Supply-chain security, including SBOM and code signing)
Q008: first = IDM (Identity, MFA and privileged access management); second = SUP (Supply-chain security, including SBOM and code signing)
Q009: first = MON (ICS network monitoring and anomaly detection); second = PHY (Physical and environmental hardening of sites)
Q010: first = SEG (Network segmentation and unidirectional gateways); second = BAK (Offline immutable backups and recovery for ICS)
Q011: first = IDM (Identity, MFA and privileged access management); second = PHY (Physical and environmental hardening of sites)
Q012: first = BAK (Offline immutable backups and recovery for ICS); second = PHY (Physical and environmental hardening of sites)
Q013: first = SUP (Supply-chain security, including SBOM and code signing); second = SEG (Network segmentation and unidirectional gateways)
Q014: first = IR (Incident response and staff training); second = IDM (Identity, MFA and privileged access management)
Q015: first = IDM (Identity, MFA and privileged access management); second = SEG (Network segmentation and unidirectional gateways)
Q016: first = BAK (Offline immutable backups and recovery for ICS); second = SUP (Supply-chain security, including SBOM and code signing)
Q017: first = SEG (Network segmentation and unidirectional gateways); second = PHY (Physical and environmental hardening of sites)
Q018: first = IR (Incident response and staff training); second = SEG (Network segmentation and unidirectional gateways)
Q019: first = IR (Incident response and staff training); second = BAK (Offline immutable backups and recovery for ICS)
Q020: first = MON (ICS network monitoring and anomaly detection); second = IR (Incident response and staff training)
Q021: first = MON (ICS network monitoring and anomaly detection); second = IDM (Identity, MFA and privileged access management)

[блоки B02–B35 не наведено]
```
