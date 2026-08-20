取得元: https://martinfowler.com/articles/talk-about-platforms.html
取得日: 2026-08-20
著者: Evan Bottcher
公開日: 2018-03-05

---

## Core Definition

A digital platform is described as "a foundation of self-service APIs, tools, services, knowledge and support which are arranged as a compelling internal product." It enables autonomous delivery teams to deploy features faster with reduced coordination needs.

## The Un-Platform Problem

The article illustrates platform failures through "BigCo," a financial services organization that retained siloed infrastructure teams (middleware, midrange, DBA, networks, etc.). Each team operated independently under separate management, creating bottlenecks. Changes requiring cross-team coordination took "weeks or multiple months," discouraging engineers from making necessary improvements.

## Backlog Coupling Concept

A critical constraint emerges when product team backlogs depend on work queues from other teams. Research cited shows tasks requiring another team's involvement are "10-12x slower in elapsed time." This dependency-driven slowdown damages accountability and team motivation.

## Key Platform Characteristics

Effective platforms must be:
- Self-service for provisioning, configuration, and management
- Composable with discrete, independently usable services
- Flexible without inflexible operational mandates
- Easy to adopt with documentation and quick-start guides
- Secure and current by default

## Autonomy vs. Standardization

The article contrasts two approaches: WebBiz granted teams complete infrastructure autonomy, boosting engagement and responsibility but increasing decision-making overhead. Netflix's concept of "the paved road" offers compelling defaults teams choose voluntarily rather than mandates.
