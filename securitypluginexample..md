sequenceDiagram
    participant FleetIDEA as Fleet IDEA
    participant PluginAPI as Fleet Plugin API
    participant SecurityPlugin as Security Analysis Plugin

    FleetIDEA->>PluginAPI: Request plugin
    PluginAPI->>SecurityPlugin: Load plugin
    SecurityPlugin->>PluginAPI: Register plugin
    PluginAPI->>FleetIDEA: Plugin ready

    loop Code analysis
        FleetIDEA->>SecurityPlugin: Send code
        SecurityPlugin->>SecurityPlugin: Analyze code for security leaks
        SecurityPlugin->>FleetIDEA: Suggest security improvements
    end
