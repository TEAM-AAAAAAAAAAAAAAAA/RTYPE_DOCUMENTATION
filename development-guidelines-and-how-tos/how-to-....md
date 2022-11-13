---
description: For our dear devs
---

# ⁉ How to ... ?

### Configure

{% content-ref url="configuration.md" %}
[configuration.md](configuration.md)
{% endcontent-ref %}

### Enemies

Enemies are defined by a type, a faction, and a movementIA in the EnemyFactory.

{% hint style="info" %}
Watch out src/ecs/EnemyFactory.hpp and .cpp
{% endhint %}

To generate a new type of enemy, you need to add it to the enum EnemyType and to the typeGeneratorMap, and add a static function to generate it.

