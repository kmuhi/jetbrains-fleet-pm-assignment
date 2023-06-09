```mermaid

sequenceDiagram
    participant FleetIDEA as Fleet IDEA
    participant PluginAPI as Fleet Plugin API
    participant SecureAccessPlugin as Secure-Access-Plugin
    participant FleetIdeaRenderEngine as Fleet Render Engine

    FleetIDEA->>PluginAPI: Request plugin
    PluginAPI->>SecureAccessPlugin: Load plugin
    SecureAccessPlugin->>PluginAPI: Register plugin
    SecureAccessPlugin->>PluginAPI: Authenticate plugin(license)
    PluginAPI->>FleetIDEA: Plugin ready

    loop File analysis
        FleetIDEA->>SecureAccessPlugin: Send opened file
        SecureAccessPlugin->>SecureAccessPlugin: Static analysis
        SecureAccessPlugin->>SecureAccessPlugin: DLP analytics
        SecureAccessPlugin->>SecureAccessPlugin: Check sensitive information leaks
        SecureAccessPlugin->>FleetIDEA: Report issues and suggestions
        SecureAccessPlugin->>FleetIdeaRenderEngine: Renders results for end user
    end
```
