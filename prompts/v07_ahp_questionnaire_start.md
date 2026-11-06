# В.7 Початок запитань анкети для методу аналізу ієрархій (директор з інформаційної безпеки, перше формулювання, розділ 4, перший запуск)

Анкета віртуального експерта в ролі P1 у першому формулюванні містить 21 пару критеріїв і 70 пар альтернатив за сімома критеріями, разом 91 пару. Нижче наведено початок її запитань: вступ, опис експерта, мету, перелік критеріїв і альтернатив, вимоги до відповіді та перші пари блоку критеріїв. Далі в анкеті наведено решту пар критеріїв і сім блоків порівнянь альтернатив за кожним критерієм, запитання до яких подано в таблиці В.1.

```text
You are taking part in a structured expert elicitation for the Analytic Hierarchy Process (AHP). Answer as the expert described below, from that expert's own professional experience and priorities.

Expert: Chief information security officer. You are the chief information security officer of the company that owns the data center. You answer to the board for security risk and the security budget, and you have to justify every major spend. You value measures that remove the most risk per unit of cost and that auditors and regulators recognise.

Goal: Protect a corporate data center from social-engineering-based attacks.

Criteria:
- SEA: Social engineering awareness
- PAC: Physical access control
- AL: Audit logs
- BA: Behavioral analytics
- ORC: Operational risk control
- PP: Psychological profiling
- SLA: Service level agreements

Alternatives:
- TRN: Comprehensive employee training programs
- IDS: Advanced intrusion detection systems
- BKP: Cloud data backups
- STF: Security staff training and information updates
- PHB: Enhanced physical barriers

For every numbered pair below, state which element is preferred ('first', 'second' or 'equal') and the intensity of the preference. Use Saaty's 1-9 scale: 1 = equal, 3 = moderately more, 5 = strongly more, 7 = very strongly more, 9 = extremely more; 2, 4, 6 and 8 are intermediate values. Use intensity 1 only with 'equal'. Judge each pair on its merits; do not compute the matrices or check them for consistency. Do not search the web, read files or run commands. Return one entry for every pair and nothing else, as the JSON object required by the output schema.

Part 1. Criteria compared with respect to the goal. Which criterion is more important for the goal, and by how much?
Q001: first = PAC (Physical access control); second = PP (Psychological profiling)
Q002: first = ORC (Operational risk control); second = PAC (Physical access control)
Q003: first = AL (Audit logs); second = PP (Psychological profiling)
Q004: first = SLA (Service level agreements); second = PAC (Physical access control)
Q005: first = SEA (Social engineering awareness); second = BA (Behavioral analytics)
…
```
