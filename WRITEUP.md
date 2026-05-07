# Write-up Template

---

### Virtual Machine (VM)

A Virtual Machine provides full control over the operating system, installed software, networking configuration, and deployment process. This option offers high flexibility and can support custom system configurations or applications with special runtime dependencies.

However, using a VM also introduces additional administrative overhead. The operating system must be maintained manually, including software updates, security patches, scaling configuration, monitoring, and deployment setup. Availability and scalability must also be configured manually.

From a cost perspective, a VM is usually more expensive because the virtual machine runs continuously, even during periods of low usage.

### App Service

Azure App Service is a Platform as a Service (PaaS) solution that simplifies deployment and hosting of web applications. The platform automatically manages the operating system, runtime environment, scaling capabilities, and deployment integration.

For this CMS application, App Service provides several advantages:
- Easy deployment directly from GitHub
- Lower administrative effort
- Built-in scalability support
- Simplified configuration management using environment variables
- Faster setup and deployment
- Lower operational complexity

The Flask CMS application is relatively lightweight and does not require low-level operating system access or special infrastructure customization. Therefore, App Service is a good fit for the project requirements.

From a cost perspective, App Service is also more efficient for small and medium web applications because lower pricing tiers are available and infrastructure management is included.

### Chosen Solution

For this project, Azure App Service was selected.

### Justification

Azure App Service was chosen because it provides a simpler and more efficient deployment model for a Flask-based web application. The service integrates directly with GitHub for automated deployment and reduces the need for server administration.

The application requirements are focused mainly on hosting a web application, connecting to Azure SQL Database, Azure Blob Storage, and Microsoft authentication services. These requirements are fully supported by App Service without requiring additional infrastructure management.

App Service also improves development workflow efficiency because deployments can be triggered automatically after pushing updates to GitHub.

---

### Assess app changes that would change your decision.

The decision could change from App Service to a Virtual Machine if the application requirements became more infrastructure-specific or required deeper operating system customization.

Examples include:
- Need for custom operating system configuration
- Installation of specialized system-level software
- Use of unsupported runtimes or libraries
- Advanced network configuration requirements
- Dedicated server requirements for compliance or security
- Hosting multiple tightly coupled services on the same machine
- Custom container orchestration outside App Service capabilities

If the CMS application evolved into a large enterprise platform with highly customized infrastructure requirements, a Virtual Machine solution could become more appropriate despite the increased operational overhead.