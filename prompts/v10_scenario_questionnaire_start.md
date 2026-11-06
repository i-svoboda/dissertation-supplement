# В.10 Початок запитань анкети для оцінювання сценаріїв атак на оператора системи розподілу (інженер АСУ ТП, перше формулювання, розділ 4, перший запуск)

Запитання кожної анкети надсилалися моделі одним запитом. Нижче наведено інструкцію та перший блок запитань (порівняння критеріїв), які отримав віртуальний експерт у ролі інженера АСУ ТП (перше формулювання, перший запуск). Далі анкета містить три блоки оцінок варіантів за критеріями П, С і З (15 оцінок) і три блоки парних порівнянь варіантів за цими критеріями (30 пар). Кожна анкета має власний порядок варіантів в описі, блоків, пунктів і елементів у парах, який задає початкове значення генератора псевдовипадкових чисел цієї анкети. Ланцюги подій варіантів ВС, ПД, КВ і СД скорочено до переліку ідентифікаторів подій, оскільки події E04, E05, E07, E08, E14 і E15 з об'єктами прив'язки взято з еталонної моделі, яка надається на запит. Друге і третє формулювання відрізняються від першого лише вступом і запитаннями до блоків. Відповідь подається одним об'єктом JSON з трьома масивами: парні порівняння (Q01–Q36), оцінки (R01–R15) та обґрунтування блоків (B1–B7).

```text
You are taking part in a structured expert elicitation for the Analytic Hierarchy Process (AHP). Answer as the expert described below, from that expert's own professional experience and priorities.

Expert: ICS engineer. You operate PLC and DCS equipment from several vendors at a critical infrastructure operator. Safety and availability come first for you, and you distrust intrusive scanning of live control systems. Other things being equal, less implementation time, cost and operational impact is better.
This expert profile was written for choosing security controls. Use the same professional experience and viewpoint to judge the scenario variants below on the criteria defined here; parts of the profile about controls or about criteria not defined here do not apply.

Goal: decide which of the five complete cyber incident scenario variants of this organization should be prioritized for review.

Organization. A modeled regional electricity distribution organization in Ukraine with generalized roles and assets. The model does not describe any real operator and contains no real network topology. It distinguishes enterprise IT, the boundary with operational technology (OT), operational control and physical processes. The case was built from the incident reports summarized below.

Initial state (A): normally operating regional electricity-distribution organization.
- Enterprise IT and operational technology services are available.
- Dispatchers retain visibility and authorized remote control.
- Substations are energized and operating normally.
- Remote administration and trusted maintenance relationships exist.
- Operator communications, backup power, and field response are available.

Target incident (B): unauthorized switching de-energizes multiple substations.
- An unauthorized switching action occurs through organizational cyber resources.
- The action de-energizes more than one substation.

Incident reports used for the case:
- December 2015, attacks on Ukrainian electricity distribution companies. Source: Lee, Assante and Conway, E-ISAC and SANS analysis, 2016; Maynard, McLaughlin and Sezer, Journal of Cybersecurity, 2020. The adversary reached operational systems through the compromised enterprise network, switched equipment without authorization and took control away from operators.
- April 2022, prevented attack on the Ukrainian energy sector. Source: State Service of Special Communications and Information Protection of Ukraine (SSSCIP) and the Government Computer Emergency Response Team of Ukraine (CERT-UA), 12 April 2022. The attack targeted substations, Windows and Linux systems, as well as network equipment simultaneously.
- 2025, national incident statistics. Source: SSSCIP, 7 January 2026. CERT-UA processed 5,927 cyber incidents in 2025, and the energy sector accounted for 279 of them.

Scenario variants. Each variant is a complete chain of events from its entry event to the target incident B. Each event is linked to the supporting object of the organization that it needs (the object's role in brackets). The material is strategic. It contains no device commands, credentials, payloads or exploit instructions.

RS: Remote service compromise (7 steps between events)
  [події E04, E06, E09–E13, B з об'єктами прив'язки; не наведено]

MP: Maintenance provider credential compromise (7 steps between events)
  [події E07, E08, E09–E13, B з об'єктами прив'язки; не наведено]

EE: Enterprise endpoint compromise (7 steps between events)
  [події E05, E06, E09–E13, B з об'єктами прив'язки; не наведено]

PC: Personnel credential compromise (9 steps between events)
  E01  A targeted message reaches a user with enterprise administration rights. Supporting object: enterprise administrator role (target).
  E02  Enterprise administrator credentials or a valid session token is leaked. Supporting object: enterprise administrator account and authentication material (target).
  E03  An unauthorized valid account session is established. Supporting object: enterprise administrator account and authentication material (target).
  E06  Enterprise administrative privilege is obtained without authorization. Supporting object: enterprise administrator account and authentication material (resource).
  E09  Administrative access to the OT support environment is obtained. Supporting object: OT support environment (target).
  E10  Unauthorized access reaches dispatch and control services. Supporting object: remote operational control service (target).
  E11  Unauthorized operational control capability is obtained. Supporting object: remote operational control service (resource).
  E12  An operator workstation accepts a switching action without a dispatcher order or switching form. Supporting object: operator workstation (resource).
  E13  Unauthorized switching commands are issued. Supporting object: remote operational control service (resource).
  B  Unauthorized switching de-energizes multiple substations. Supporting object: distribution substations (target).

DS: Dispatcher session takeover (5 steps between events)
  [події E14, E15, E11–E13, B з об'єктами прив'язки; не наведено]

Criteria. A higher value on any criterion means a higher priority for review.
- L, likelihood: higher means stronger support for the path from the case and the incident reports. It grades the strength of the evidence for the path; it is not the frequency of attacks. Anchored scale: 1-3 weak evidence; 4-6 evidence that depends on additional assumptions; 7-9 strong confirmation by the case or sources.
- D, path directness: higher means a shorter chain of events to the target incident. It is rated from the path length: 9 for five or fewer steps between events on the path to the incident, 7 for six or seven, 5 for eight and 3 for nine or more. It follows from the chains above and is not asked below.
- F, attack feasibility: higher means easier for the adversary. Anchored scale: 1-3 high effort or difficult preconditions; 4-6 moderate effort with access requirements; 7-9 easy entry through exposed or trusted access paths.
- C, detection complexity: higher means harder to detect early. Anchored scale: 1-3 strong early signals; 4-6 partial visibility; 7-9 limited early visibility.
All variants end in the same target incident, so their consequences are the same and are not a criterion.

How to answer. For every numbered pair, state which element is preferred ('first', 'second' or 'equal') and the intensity of the preference. For two criteria, the preferred one is the more important one for the goal; for two scenario variants, it is the variant that stands higher on the stated criterion. Use Saaty's 1-9 scale: 1 = equal, 3 = moderately more, 5 = strongly more, 7 = very strongly more, 9 = extremely more; 2, 4, 6 and 8 are intermediate values. Use intensity 1 only with 'equal'. For every rating item, give one whole number from 1 to 9 on the anchored scale of the stated criterion. Judge each item on its merits; do not compute matrices, scores or rankings and do not check the answers for consistency. For every block, give one short justification of one or two sentences at the level of the scenario descriptions, without device commands, exploit details or other technical attack instructions. Do not search the web, read files or run commands. Return one entry for every pair, every rating item and every block, and nothing else, as the JSON object required by the output schema.

Block B1. Criteria compared with respect to the goal. Which criterion is more important for the goal, and by how much?
Q01: first = D (path directness); second = C (detection complexity)
Q02: first = F (attack feasibility); second = L (likelihood)
Q03: first = F (attack feasibility); second = C (detection complexity)
Q04: first = F (attack feasibility); second = D (path directness)
Q05: first = L (likelihood); second = D (path directness)
Q06: first = C (detection complexity); second = L (likelihood)

[блоки B2–B7 не наведено]
```
