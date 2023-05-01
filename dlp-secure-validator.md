```mermaid

sequenceDiagram
    participant FleetIDEA as Fleet IDEA
    participant PluginAPI as Fleet Plugin API
    participant SecureAccessPlugin as Secure-Access-Plugin

    FleetIDEA->>PluginAPI: Request plugin
    PluginAPI->>SecureAccessPlugin: Load plugin
    SecureAccessPlugin->>PluginAPI: Register plugin
    PluginAPI->>FleetIDEA: Plugin ready

    loop File analysis
        FleetIDEA->>SecureAccessPlugin: Send opened file
        SecureAccessPlugin->>SecureAccessPlugin: Static analysis
        SecureAccessPlugin->>SecureAccessPlugin: DLP analytics
        SecureAccessPlugin->>SecureAccessPlugin: Check sensitive information leaks
        SecureAccessPlugin->>FleetIDEA: Report issues and suggestions
    end
```
