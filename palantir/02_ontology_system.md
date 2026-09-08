# Palantir Ontology System(交付核心)

> 来源:Palantir 官方文档 Architecture Center - The Ontology system
> 原文:https://www.palantir.com/docs/foundry/architecture-center/ontology-system/

The Ontology is the system at the heart of Palantir’s architecture. The Ontology is designed to represent the complex, interconnected
decisions
of an enterprise, not simply the data. This enables both humans and AI agents to collaborate, across operational workflows that must orchestrate with the physical world.
An airline might model flights, aircraft, crew manifests, scheduling optimizers, and other fragmented enterprise assets into their ontology, to power day-of flight operations and longer-range planning.
A hospital system might instead model patients, nurse schedules, medical supplies, bed capacities, and other elements that often shift in real-time, and are essential to driving the patient lifecycle.
In military contexts, an ontology can unify the readiness information across forward-deployed forces with the operational processes that underpin reconnaissance and target selection, providing a shared operational world for multinational teams.
How the Ontology models decisions
The Ontology models decisions through the four-fold integration of
data
logic
action
, and
security
Data
can flow from every conceivable source, such as fragmented ERP estates, homegrown systems of record, CRMs, industrial databases, geospatial repositories, real-time sensors, document stores, and essentially any other digital alcove. The Ontology unifies these disparate data sources into coherent objects, properties, and links; the semantic concepts which enable the full range of stakeholders to interact with and manipulate the information.
The data objects, or "nouns", however, must be complemented by "verbs" in order to model decisions; semantics must be paired with kinetics. The Ontology is designed to model the full range of
actions
, from simple transactions to complex multi-step updates that must be written back to operational and edge systems in real time.
that powers each action can be modular and evolve over time, reflecting the diversity of calculation and reasoning that drives decision-making. The logic underlying a given action (or enhancing a particular object) could be a simple business rule, a conventional machine learning model, an LLM-driven function, or a complex multi-step orchestration that involves several compute engines.
To illustrate the vital role of
(and how it is woven into data, logic, and actions), we can use the example of a notional medical manufacturing company that is leveraging the Ontology.
Ontology example: Medical manufacturing
Imagine a medical manufacturer that must manage a complex web of vendor interactions, production lines, logistics activities, and customer lifecycles.
Their ontology models the manufacturing plants, work orders, customer details, inbound packages, outbound shipments, and other key semantic concepts that integrated together hundreds of underlying data sources.
For the supply chain analysts, production engineers, warehouse associates, and other team members interacting with the Ontology, different scopes of access are relevant.
The production teams might require access to see global telemetry pertaining to machines and the lifecycle of finished goods;
Warehouse associates might have more granular restrictions based on a team member’s regional location;
Supply chain analysts may have even more granular permissions, which apply row/column-level restrictions to sensitive data elements based on particular user.
As these different teams build AI-powered agents, they must have security scopes that either inherit from a human user, or from the permissions structure of a defined project. This becomes much more complex when factoring in the action and logic primitives that are connected into the Ontology, and are essential to conducting workflows.
The ability to trigger a purchase order might have granular permissions, while the ability to run a scenario to gauge the impact of a proposed reallocation might be more permissible; the underlying optimizers, or abilities to call LLMs, which manifest into functions which are interactively orchestrated via actions, might have altogether different security scopes. The Ontology’s security system has to reconcile all of these granular policies, at the time of interaction, across tens of thousands of humans and agents.
The Ontology Language, Ontology Engine, and Ontology Toolchain
The Ontology is not a "semantic layer"; the fourfold integration and operationalization of data, logic, action, and security cannot be accomplished with a thin semantic layer or a monolithic design.
Rather, the Ontology is a multimodal system consisting of dozens of underlying components, which can conceptually be grouped into a Language, an Engine, and Toolchain.
Language
models the semantic objects, links, and properties; along with the kinetic actions and automations; and the literal pieces of logic that define how those actions operate, and how they interact with other systems.
Engine
substantiates every component of the Language. It provides the modular read architecture that enables high-scale SQL queries, real-time subscription to state changes, and every materialization needed by mixed Human + AI teams. In equal measure, it provides a scalable write architecture which enables atomic and durable transactional updates, high-scale batch mutations, high-scale streams, and mechanisms like Change Data Capture for extremely low-