# 4. Схема згенерованого JSON-документа (розділ 2)

Кожен згенерований JSON-документ перевіряється за JSON-схемою (JSON Schema, draft 2020-12). JSON-документ, що не відповідає схемі, відхиляється автоматично. Основні поля схеми такі:

– `case_id`, `run_id`, `role_id`, `role_label`, `primary_dimension` – ідентифікатори прикладу, запуску, ролі агента й аспекту опису організації (один із шести аспектів В.3);

– `object_nodes` (щонайменше 4) – вершини ієрархії об'єктів з полями `id`, `label`, `node_type` (`state_root`, `domain`, `object`, `interface`, `dependency`, `resource`), `object_class` (11 класів: `organization` – організація (корінь), `domain_container` – домен, `person_role` – роль персоналу, `identity` – обліковий запис, `service` – сервіс, `system` – система, `interface` – інтерфейс, `communication_channel` – канал зв'язку, `power_resource` – ресурс живлення, `external_relationship` – зовнішні відносини, `response_resource` – ресурс реагування), `domain` і `initial_attributes` з обов'язковими атрибутами `availability`, `trust`, `connectivity`;

– `object_edges` (щонайменше 3) – структурні зв'язки «батько – нащадок» з полями `parent`, `child`, `relation` (`consists_of`, `contains`, `has_interface`, `has_dependency`) і `rationale`;

– `event_nodes` (щонайменше 4) – події з полями `id`, `label`, `node_type` (`target_event`, `causal_event`), `event_class` (8 класів: `contact` – контакт, `identity_change` – зміна ідентифікаційних даних, `access` – доступ, `control` – керування, `operational_action` – оперативна дія, `operational_effect` – оперативний наслідок, `recovery_impairment` – погіршення відновлення, `response_requirement` – вимога реагування), `domain`, `predecessor_logic` (`single`, `all_of`, `any_of`), `observable_result` і `required_roles`;

– `required_roles` (щонайменше одна на подію) – ролі об'єктів, потрібних події, з полями `role` (`actor`, `target`, `channel`, `resource`), `object_class`, `scope` (`initial_state`, `external`), `mandatory` і `required_attributes`;

– `causal_edges` (щонайменше 3) – причинні зв'язки з полями `cause`, `effect`, `relation` (`enables`, `causes`, `contributes_to`), `logic_group` і `rationale`;

– `uncertainties` – необов'язковий перелік невизначеностей, які агент не зміг розв'язати.

Схема не допускає полів, які в ній не описано. Модель не створює в JSON-документі зв'язків «об'єкт – подія», оскільки вони встановлюються після об'єднання JSON-документів (див. підрозділи 2.1 і 2.2).
