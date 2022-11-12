# Examples



Now that we have a better visualization of what composes the ecs, we can see how we can use it.

Now let's decompose our main function who's actually creating a world, spawn two entities and gives the player the possibility to move and shoot :

```cpp
int main()  
{  
    ecs::Engine engine;
    
    // initialization of the world
    ecs::World ourNewWorld = getGameWorld(engine);
    
    // set the world as ready to use
    engine.setWaitingWorld(ourNewWorld);  

	// run the engine
    engine.run();  
    return 0;  
}
```

### Initialization of the world

```cpp
ecs::World getGameWorld(ecs::Engine &engine)  
{  
	// In this example just below, to begin we can see a creation of a new world
    ecs::World world(engine.getWindow());  

	// After that we are able to create our first entity
    ecs::Entity player = world.registry.spawn_entity();
    
	// it's now time to create a new entity and to add its associated components
    world.registry.addComponent<ecs::component::Position>(player, {10, 10});  
    world.registry.addComponent<ecs::component::Velocity>(player, {5, 5});  
    world.registry.addComponent<ecs::component::Size>(player, {2, 2});  
    world.registry.addComponent<ecs::component::Direction>(player, {1, 0});
    
	// To finish, we now want to add associated systems
    world.addSystem(ecs::systems::positionLogger);  
    world.addSystem(ecs::systems::movement);   
    return world;  
}
```

### Set the world

```cpp
void setWaitingWorld(ecs::World world, bool worldSwitchReady = true)  
{  
	// Delete the previous world in waiting mode
    if (_waitingWorld)  
        _waitingWorld.release();
    
    // Set the \_waitingWorld with the world given as parameters
    _waitingWorld = std::make_unique<ecs::World>(world);

	// Set the \_worldSwitchReady, true by default
    _worldSwitchReady = worldSwitchReady;  
}
```

### Run the Engine

```cpp
void run()  
{  
    while (_window->isOpen()) {
    
	    // Simply loop on every systems and run them
        _currentWorld->runSystems();
        
        // if the current world is ready to switch, an automaticaly switch occure
        if (isWorldSwitchReady())  
            switchWorlds();  
    }  
}
```
