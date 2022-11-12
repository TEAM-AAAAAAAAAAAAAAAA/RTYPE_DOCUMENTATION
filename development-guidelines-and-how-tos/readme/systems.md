# Systems

Systems are the things that directly interacts with components. They actually get all the associated components in order to actualize Entities' values. They are generated in lambda format and pushed in the private vector of the current world. They look like this :

```cpp
std::function<void(World &)> movement = [](World &world) {  

	// Get all the components related to the system
    auto &positions = world.registry.getComponents<component::Position>();  
    auto const &velocities = world.registry.getComponents<component::Velocity>();  
    auto &directions = world.registry.getComponents<component::Direction>();  
    using chrono = std::chrono::high_resolution_clock;
    static auto clock = chrono::now();
    
    // Loop on every components and apply the logic of the system
    for (size_t i = 0; i < positions.size() && i < velocities.size(); ++i) {  
        auto &pos = positions[i];  
        auto const &vel = velocities[i];  
        auto &dir = directions[i];  
        if (pos && vel) {
 
        // The goal of this is to update Entities values
            if (std::chrono::duration<double, std::milli>(chrono::now() - clock).count() > 10) {  
                pos.value().x += vel.value().x * (dir.value().x);  
                pos.value().y += vel.value().y * dir.value().y;  
                dir.value().x = 0;  
                dir.value().y = 0;  
                clock = chrono::now();  
            }  
        }  
    };  
};
```
