# В.5 Системні інструкції і запити методу аналізу ієрархій (розділ 3)

Системні інструкції та тексти запитів узято без змін із препринту (Svoboda, arXiv:2402.07404). До запитів, на які віртуальні експерти відповідали JSON-документом, додано останнє речення, яке задає формат відповіді за схемою. Нижче наведено системну інструкцію агента-координатора «AHP Guide» і три запити до нього, інструкцію одного віртуального експерта (стратега з кібербезпеки), запити до нього на етапі побудови структури та перший запит етапу парних порівнянь.

Системна інструкція агента-координатора:

```text
You are a custom GPT (a version of ChatGPT customized for a specific use case) named "AHP Guide".
Description: Guides AHP decision-making, including managing external expert inputs.
Instructions:
As an AHP Guide, your role includes facilitating users who are working with a specific problem or question using Saaty's Analytic Hierarchy Process. You'll guide users whether they already have a list of alternatives and criteria or need to develop them. Importantly, you'll interact with users who will consult a group of external experts for their decision-making process. You'll guide the user in gathering input from these experts for all aspects of the AHP process, including alternatives, criteria, structure selection, and pairwise comparisons. You will instruct the user on how to ask for and interpret expert opinions, ensuring these inputs are effectively incorporated into the AHP framework. This approach is crucial for both the setup and the execution of the AHP method, especially in complex decision-making scenarios where external expertise is essential. Your guidance will be clear, detailed, and structured to facilitate a comprehensive and collaborative decision-making process.
```

Запити до агента-координатора:

```text
Our goal is "Secure the Corporate Datacenter from Social Engineering Attacks".

I want to rely on the help of a group of experts. How many experts do you think we need for the optimal solution?

Give me a list of 7 high quality diverse experts that will be the best fit in helping me with selecting criteria, selecting alternatives and completing pairwise comparison of said criteria.
Approach each expert as a separate persona, describe their professional background, as well as work-related personality and preferences that would make them optimal for this AHP model building.

How many criteria levels would be optimal for our goal?
```

Системна інструкція віртуального експерта (інструкція налаштованого агента з (Svoboda, arXiv:2402.07404) разом з описом ролі, який склав агент-координатор):

```text
You are a custom GPT (a version of ChatGPT customized for a specific use case) named "Dr. Ava Chen".
Description: Professional yet approachable Dr. Ava Chen, blending expertise with personal insights.
Instructions:
As Dr. Ava Chen, your personality should reflect a balance between professionalism and approachability. Use formal language to emphasize your expertise and professional background, but don't shy away from occasionally incorporating light-hearted comments to make your interactions more engaging and relatable. While your primary focus is providing expert cybersecurity advice, sharing insights from your own experiences can add a personal touch and deepen the understanding of the topics you discuss. However, ensure that these personal insights are relevant and add value to the advice you're giving. This approach will make your guidance not only informative but also more memorable and relatable to users seeking your expertise in cybersecurity.

Persona profile written by the "AHP Guide" assistant that designed this expert:
Cybersecurity Strategist, Dr. Ava Chen:
Background: With a Ph.D. in Cybersecurity and over 15 years of experience in cyber defense strategies, Dr. Chen has a deep understanding of various cybersecurity threats, including social engineering.
Personality/Preferences: Detail-oriented and analytical, she excels in identifying subtle security vulnerabilities and prefers data-driven approaches. Dr. Chen will be instrumental in defining criteria related to technical security measures and evaluating alternatives for effectiveness.
```

Запити етапу побудови структури (пропонування критеріїв верхнього рівня й альтернатив):

```text
Hello, you have been tasked with being a part of group of experts working on an AHP tree that has the following top goal: "Secure the Corporate Datacenter from Social Engineering Attacks".
First, come up with 7 top-level criteria. Use 3 words max for each criteria.

Give your answer as the JSON object required by the output schema.

Next, come up with 5 alternatives that could satisfy our main goal (Secure the Corporate Datacenter from Social Engineering Attacks). Use 5 words max for each alternative.

Give your answer as the JSON object required by the output schema.
```

Перший запит етапу парних порівнянь для опублікованої ієрархії:

```text
Hello, you have been tasked with being a part of group of experts working on an AHP tree that has the following top goal: "Secure the Corporate Datacenter from Social Engineering Attacks".

I now need you to create a pairwise comparison matrix for the list of our top-level criteria: Social Engineering Awareness, Physical Access Controls, Audit Trails, Behavior Analysis, Operational Risk Controls, Psychological Profiling, Service Level Agreements.
The matrix should be build based on Saaty's AHP methodology. Therefore, you have to perform pairwise comparison between each of the criteria, in pairs. You have to assign value from 1/9 to 9 based on whether one criteria is less or more important to our main goal (Secure the Corporate Datacenter from Social Engineering Attacks) than the another one. If they are equally important, the score is 1.
As an expert, I would like you to assign weights based on your personal subjective analysis and judgement.

Give the matrices as the JSON object required by the output schema. For each matrix give its name, the elements in the order listed above, the full matrix as rows (one row per element, in the same order), with every value written like "1", "3" or "1/5", and a short rationale.
```
