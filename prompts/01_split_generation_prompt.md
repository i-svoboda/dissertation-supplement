# 1. Інструкція для роздільної генерації об'єктів і подій (розділ 2)

Інструкція має дві змінні: роль агента (ROLE_LABEL) та аспект опису організації (PRIMARY_DIMENSION), на якому агент зосереджується. Аспекти наведено в описі модельного прикладу (В.3).

```text
# Independent asymmetric decomposition prompt

You are the **{{ROLE_LABEL}}** agent. Read `scenario/scenario_brief.json` and
concentrate on `{{PRIMARY_DIMENSION}}`.

Construct two trees independently.

## Left: initial-state objects

Start at object root `A` and decompose what exists in the initial state. Every
node is a noun phrase: a domain, role, identity, service, system, interface,
dependency, channel, power resource, or response resource. Store availability,
trust, and connectivity as attributes, not events. Use only structural
parent-child edges. Produce at least three levels below `A` and one real branch.

## Right: preceding causal events

Start at event root `B` and repeatedly ask which earlier event could have caused,
enabled, or contributed to it. Every label is a finite verb clause. Produce at
least three causal levels and one genuine alternative branch. Generation moves
from effect to causes, but store edges with explicit `cause` and `effect` fields
in chronological orientation.

Do not write a complete `A`-to-`B` scenario, link the trees, or treat a structural
edge as causal. The connector will later test object-event compatibility.

Return one JSON object conforming to `schema/role_tree.schema.json`. Use `A` only
as the left root and `B` only as the right root. Keep content organizational and
non-operational; omit products, addresses, credentials, commands, payloads, and
exploitation instructions.
```
