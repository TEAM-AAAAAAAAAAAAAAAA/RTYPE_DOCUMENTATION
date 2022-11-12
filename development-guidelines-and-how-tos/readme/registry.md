# Registry

This is the most interesting part if we talk about managing components because it's the **Components Manager** by definition. It consists of two main methods :

```cpp
template <class Component> SparseArray<Component> &registerComponent()
```

This function is not used by the developper but it allows, in back end, a new type of components in the registry. In the same way, the component stores a self delete methods as a lambda in a `_eraseFunc` private vector.

```cpp
typename SparseArray<Component>::referenceType addComponent(Entity const &to, Component &&c)
```

If your objective is to add a new component to the Sparse Array, you are at the right place. Let's just define what a world is before giving you a good example of adding a component and making it run properly.

Registry Class Private Member

```cpp
std::unordered_map<std::type_index, std::any> _componentsArrays;
```

It represents the group of components already registred by the registerComponent method

```cpp
std::vector<std::function<void(Registry &, Entity const &)>> _eraseFunctions;  
```

It represents the vector of self erase lambda of each component

```cpp
std::vector<std::size_t> _entitiesBin;  
```

It represents the bin of every deleted entities, used to recover an entity instead of creating another one

```cpp
std::size_t _lastEntity;
```

It represents the current number of entities used or able to be used in the Registry Class

***
