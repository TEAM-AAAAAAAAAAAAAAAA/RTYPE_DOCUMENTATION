---
description: How to use our ECS
---

# 📕 ECS MANUAL

Before explaining systems and components' methods, lets have a look on the architecture diagram of the ECS.

> Just note that there is no trash struct called Entity\_t containing the whole of the data. Entity are only represented by ID/index and which component is assigned on this ID

Here you will find definitons of the terms in an increasing architectural way

{% content-ref url="components.md" %}
[components.md](components.md)
{% endcontent-ref %}

{% content-ref url="sparse-array.md" %}
[sparse-array.md](sparse-array.md)
{% endcontent-ref %}

{% content-ref url="systems.md" %}
[systems.md](systems.md)
{% endcontent-ref %}

{% content-ref url="registry.md" %}
[registry.md](registry.md)
{% endcontent-ref %}

{% content-ref url="worlds.md" %}
[worlds.md](worlds.md)
{% endcontent-ref %}

{% content-ref url="examples.md" %}
[examples.md](examples.md)
{% endcontent-ref %}

{% content-ref url="a-word-on-singletons.md" %}
[a-word-on-singletons.md](a-word-on-singletons.md)
{% endcontent-ref %}



## See also

{% content-ref url="../network/" %}
[network](../network/)
{% endcontent-ref %}

{% content-ref url="../configuration.md" %}
[configuration.md](../configuration.md)
{% endcontent-ref %}
