# 2. Інструкція для локального уточнення (розділ 2)

Інструкція надсилалася під час ітерацій уточнення. Її змінні містять опис обраної прогалини та межові вершини ієрархії об'єктів і ланцюга подій, від яких продовжується розгортання.

```text
# Targeted asymmetric local-decomposition prompt

You are the **{{ROLE_LABEL}}** agent. A coverage audit for case `UA-EDO-02`
identified this gap:

`{{GAP_DESCRIPTION}}`

Object frontier: `{{OBJECT_FRONTIER}}`

Event frontier: `{{EVENT_FRONTIER}}`

Refine only the deficient local material. If an object is too general, split its
noun branch into more specific objects or interfaces using structural edges. If
an event is too broad, regress its verb branch into atomic predecessor events
using explicit `cause` and `effect` fields. If both lack detail, expand them
independently. If precise nodes are incompatible, record uncertainty instead of
manufacturing a connection.

For every expanded side, provide at least three local levels and one material
branch. Do not generate a bridge or complete scenario. Return JSON conforming to
`schema/role_tree.schema.json` with `run_id` prefixed by `targeted_`. Only the
connector may create typed grounding links. Keep the output non-operational.
```
