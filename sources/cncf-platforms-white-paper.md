取得元: https://tag-app-delivery.cncf.io/whitepapers/platforms/
取得日: 2026-08-20

---

## Introduction

The paper discusses how platform engineering has emerged as an explicit form of DevOps cooperation in enterprises. Platforms curate foundational capabilities, frameworks, and experiences for internal customers like application developers and data scientists. The document aims to support enterprise leaders and platform team leaders in advocating for and planning internal cloud computing platforms by examining platform value, measurement approaches, and implementation strategies.

## Why Platforms?

Process improvements over recent decades have increased software team agility but shifted infrastructure responsibilities to product teams, consuming their cognitive resources. Organizations implement platforms to:

1. Reduce cognitive load on product teams, accelerating development
2. Improve product reliability through expert configuration and management
3. Accelerate delivery via tool and knowledge reuse across teams
4. Reduce security, regulatory, and functional risks through governed capabilities
5. Enable cost-effective cloud service use while maintaining user experience control

Platform teams multiply impact by serving many product teams, consolidate common functionality for easier governance, and enable consistent experiences that facilitate knowledge sharing and quick developer onboarding across products.

## What is a Platform

"A platform for cloud-native computing is an integrated collection of capabilities defined and presented according to the needs of the platform's users." Platforms provide consistent experiences for acquiring and integrating typical capabilities across applications and use cases through web portals, project templates, and self-service APIs.

Platforms don't necessarily implement all capabilities themselves; managed service providers or internal teams can maintain backing implementations while platforms provide consistency across them. A platform could be as simple as a wiki with standard operating procedures.

### Platform Maturity

Platforms progress through maturity levels:

1. On-demand capability provisioning (compute, storage, databases, identities)
2. Service space provisioning for pipelines, artifacts, and telemetry
3. Third-party software dependency provisioning
4. Complete environment templates combining runtime and development services
5. Observable functionality, performance, and cost tracking via automatic instrumentation

## Attributes of Platforms

Successful platforms exhibit these characteristics:

1. **Platform as Product**: Designed and evolved based on user requirements, prioritizing common use cases over single-team-specific features
2. **User Experience**: Consistent interfaces across GUIs, APIs, CLIs, IDEs, and portals meeting users where they are
3. **Documentation and Onboarding**: Comprehensive documentation, examples, and reusable templates (golden paths) accelerating user adoption
4. **Self-Service**: Autonomous, automatic capability requests with minimal manual intervention
5. **Reduced Cognitive Load**: Encapsulated implementation details, hidden complexity, users not responsible for service operations
6. **Optional and Composable**: Product teams can use partial offerings or provide their own capabilities when needed
7. **Secure by Default**: Built-in security with compliance validation based on organizational standards

## Attributes of Platform Teams

Platform teams should:

1. Research user requirements and plan feature roadmaps
2. Market, evangelize, and advocate for platform value
3. Develop and maintain interfaces (portals, APIs, documentation, templates, CLIs)

Platform teams focus on user requirements through interviews, hackathons, issue tracking, surveys, and usage observation. They drive adoption through internal marketing, engaging demonstrations, and regular feedback sessions.

Critically, platform teams typically don't run underlying compute, network, or storage services. They maintain interfaces while relying on externally-provided services from managed providers or infrastructure teams. They build proprietary capabilities only when unavailable elsewhere.

## Challenges with Platforms

Key implementation challenges include:

1. Treating platforms as customer-facing products requiring user partnership
2. Carefully selecting initial priorities and engaged partner teams
3. Securing enterprise leadership support demonstrating value stream impact

Platform teams face cognitive load from diverse responsibilities. Mitigation strategies include:

- Building the thinnest viable platform layer over managed provider implementations
- Leveraging open source frameworks for documentation and templates
- Ensuring appropriate platform team staffing relative to customer count

## How to Measure Platform Success

### User Satisfaction and Productivity

- Active users, retention, capabilities provisioned, user growth/churn
- Net Promoter Score or satisfaction surveys
- Developer productivity metrics (SPACE framework)

### Organizational Efficiency

- Request-to-fulfillment latency for services
- Build-and-deploy latency for new services
- Time for new users to submit initial code changes

### Product and Feature Delivery

DORA metrics tracking:
- Deployment frequency
- Lead time for changes
- Time to restore services after failure
- Change failure rate

Ultimate success measures the impact on organizational products and customer value delivery.

## Capabilities of Platforms

Platforms typically offer:

1. **Web portals** for observing and provisioning capabilities
2. **APIs and CLIs** for automatic provisioning
3. **Golden path templates and documentation** for optimal capability use
4. **Build and test automation**
5. **Delivery and verification automation**
6. **Development environments** (hosted IDEs, remote tools)
7. **Observability** (instrumentation, dashboards, cost tracking)
8. **Infrastructure services** (compute runtimes, networks, storage)
9. **Data services** (databases, caches, object stores)
10. **Messaging and event services**
11. **Identity and secret management**
12. **Security services** (code analysis, runtime analysis, policy enforcement)
13. **Artifact storage** (container images, packages, binaries, source code)

The document includes a table mapping capabilities to example CNCF/CDF projects supporting each domain.
