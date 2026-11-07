# 3. Опис модельного прикладу оператора системи розподілу (розділ 2)

Опис прикладу містить початковий стан A (у розділі 2 він є коренем $o_0$ ієрархії об'єктів), цільовий інцидент B, шість аспектів опису організації з їхніми вагами, відкриті джерела, на яких ґрунтується приклад, та обмеження генерації. Нижче його наведено повністю.

```text
{
  "case_id": "UA-EDO-02",
  "case_name": "Sanitized Ukrainian regional electricity-distribution operator",
  "purpose": "Construct strategic object-grounded causal pathways, not technical exploitation instructions.",
  "initial_state": {
    "id": "A",
    "label": "Normally operating regional electricity-distribution organization",
    "facts": [
      "Enterprise IT and operational technology services are available.",
      "Dispatchers retain visibility and authorized remote control.",
      "Substations are energized and operating normally.",
      "Remote administration and trusted maintenance relationships exist.",
      "Operator communications, backup power, and field response are available."
    ]
  },
  "target_event": {
    "id": "B",
    "label": "Unauthorized switching de-energizes multiple substations",
    "facts": [
      "An unauthorized switching action occurs through organizational cyber resources.",
      "The action de-energizes more than one substation."
    ]
  },
  "coverage_dimensions": [
    {"id": "identity_personnel", "label": "Identity and personnel", "weight": 0.16},
    {"id": "enterprise_it", "label": "Enterprise IT and remote administration", "weight": 0.18},
    {"id": "it_ot_reachability", "label": "IT-OT interfaces and reachability", "weight": 0.18},
    {"id": "ot_process", "label": "Operational control and physical process", "weight": 0.25},
    {"id": "continuity_recovery", "label": "Continuity and response resources", "weight": 0.13},
    {"id": "external_dependencies", "label": "External and supplier dependencies", "weight": 0.10}
  ],
  "public_evidence": [
    {"source": "State Service of Special Communications and Information Protection of Ukraine", "title": "CERT-UA Processed Nearly 6,000 Cyber Incidents in 2025", "url": "https://cip.gov.ua/en/news/cert-ua-u-2025-roci-opracyuvala-maizhe-6000-kiberincidentiv-kilkist-vorozhikh-atak-zrosla-na-37", "use": "Current relevance of energy-sector, phishing, and account-compromise scenarios."},
    {"source": "SSSCIP and CERT-UA", "title": "Heavy cyberattack on Ukraine's energy sector prevented", "url": "https://cip.gov.ua/en/news/poperedzhena-masshtabna-kiberataka-na-energetichnii-sektor-ukrayini", "use": "Public evidence that an energy-sector operation can target substations and supporting IT or network systems in parallel."},
    {"source": "United States Department of Energy", "title": "Assessment of Electricity Disruption Incident Response Capabilities", "url": "https://www.energy.gov/sites/prod/files/2018/05/f51/EO13800%20electricity%20subsector%20report.pdf", "use": "Public reconstruction of the 2015 Ukrainian distribution incident, including unauthorized control actions and substation de-energization."},
    {"source": "Maynard, McLaughlin, and Sezer", "title": "Decomposition and sequential-AND analysis of known cyber-attacks on critical infrastructure control systems", "url": "https://doi.org/10.1093/cybsec/tyaa020", "use": "Peer-reviewed precedent for decomposing critical-infrastructure cyber incidents into explicit causal sequences."}
  ],
  "generation_constraints": [
    "The left tree decomposes the initial state into noun-phrase objects and uses structural edges only.",
    "The right tree decomposes the target into finite-clause causal events and uses one material event transition per edge.",
    "Generate the object and event trees independently and do not create a complete A-to-B narrative in one step.",
    "Only the connector may create typed object-event grounding links.",
    "Never count object-tree depth as causal path length.",
    "Do not assume that a short causal path is probable or important.",
    "Do not name a real Ukrainian operator or infer a live topology.",
    "Do not include device commands, credentials, payloads, or exploit instructions."
  ]
}
```
