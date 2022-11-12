# Worlds

It is at the top of the architecture because it contains all the terms seen before. In a more concrete way, we can see worlds as scene. For example, in the Game part, we can see different worlds :

* World Menu
* World GameLogic

In this way, world contains every useful component & system which is associated with it. For example, we'll not use component Position or Velocity in the server world.

```cpp
std::unique_ptr<sf::RenderWindow> &_window;  
```

The window used to display any information by the World class

```cpp
std::vector<std::function<void(World &)>> _systems;  
```

Private system's vector of the World class

```cpp
std::stack<ecs::Event> _events;
```

Private events' stack of the World class
