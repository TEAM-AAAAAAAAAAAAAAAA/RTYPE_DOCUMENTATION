# Sparse Array

It's a wrapper around a std::vector used to store components of Entities. It got all the utility as a normal vector (end(), begin()...). The special feature of the SparseArray class is that its size never gets smaller. Even if an Entity disapears or is deleted, we only put a `std::nullopt` at his component location, in this way it could be reused after. Sparse array Class private members :

```cpp
std::vector<std::optional<Component>> _data
```

It represents the vector of each component in the current world.
