---
title: "How to get an AI coding agent to write SAP code that fits the design"
seo_title: "AI Coding Agents for SAP Need a Build Plan | Xveave"
description: "A coding agent given a prompt guesses. Given a build plan drawn from the approved design, it builds what was agreed. What that plan must contain."
slug: ai-coding-agents-sap-build-plan
date: 2026-11-21
author: Vinod Kumar
product: DesignVeave
---

# How to get an AI coding agent to write SAP code that fits the design

Give it a build plan instead of a prompt. An AI coding agent can write good ABAP, but it knows nothing about your project: what was agreed, which objects already exist, or why the requirement is there. A build plan drawn from the approved design supplies exactly that, and it is the difference between code that compiles and code that does what the business asked for.

## Why do coding agents struggle with SAP work?

The difficulty is rarely the language. It is everything around it.

**The agent does not know the design.** A prompt such as “build a sales order upload” leaves out which fields are mandatory, how errors are handled, and who is allowed to run it. The agent fills each gap with a reasonable guess, and reasonable guesses are how a build drifts from its specification.

**It does not know your system.** Naming conventions, package structure, the custom objects already in place, the standard interfaces your project has chosen to use: none of this is in the model. Without it, an agent may invent what it should have reused.

**It does not know what “done” means.** Without test cases, the only check is that the code activates.

**The developer becomes the context.** In practice someone pastes pieces of the specification into a chat window, one object at a time. That works for a single program. Across two hundred objects it is slow, inconsistent between developers, and leaves no record of what the agent was actually told.

## What is a build plan?

A build plan turns a technical specification into ordered, checkable work. For one development object it sets out:

- the objects to create or change, in the order they depend on each other
- their names and packages, following the project’s conventions
- the standard objects to reuse, so the agent does not rebuild them
- the logic each piece must implement, traced to the requirement behind it
- the tests that show it works

It is written for a reader that takes instructions literally. Anything left unstated will be decided by the agent.

## Where does a build plan come from?

From the design, in three steps.

A gap that the business has approved becomes a **functional specification**: what the object must do, in business terms.

That becomes a **technical specification**: how it will be built. This is where a developer’s judgment belongs. Which enhancement technique, which standard interface, how to handle volume. These are decisions, and they should be made by a person before any code is generated.

The technical specification becomes the **build plan**. By this point the choices have been made, and what remains is execution.

The order matters. Teams that ask an agent to design and build in one step get the agent’s design. Teams that settle the design first get their own.

## How does the agent receive the plan?

Through the Model Context Protocol, or MCP, an open standard that lets an AI agent read data from other systems and call their tools.

The build plan is served over an MCP server. The developer’s coding agent connects to it, reads the plan for the object in hand, connects to the SAP system, and generates the code there. Nobody copies a specification into a chat window, and every developer’s agent works from the same plan.

Because the plan is served through an open standard, the choice of agent stays with the developer. The plan does not depend on any one tool.

## Does this cover configuration as well?

In part. Much of an SAP implementation is configuration, and the same design can produce a **configuration cookbook**: the settings to make, with their values, in order, each traced to the decision that requires it.

Some of that configuration can then be created directly in the system. Not all of it can, because SAP limits what can be created that way, and the rest is carried out by a consultant following the cookbook. It is worth being plain about that boundary. A tool that claims to configure everything should be asked how.

## What stays with people?

More than the phrase “code generation” suggests.

- **The decisions.** The technical specification is reviewed and approved before a plan exists.
- **The review.** Generated code goes through the same code review and quality checks as any other.
- **The transport.** What moves to test and production, and when, remains a human decision.
- **The testing.** The plan’s tests show that the object works. Whether the process works end to end is still for the business to confirm.

The agent removes typing. It does not remove responsibility.

## Where DesignVeave fits

DesignVeave covers this chain as one product. It holds the process design, identifies the gaps, and turns approved gaps into a functional specification, a technical specification and a build plan. The build plan is served over an MCP server, so any coding agent can connect to the SAP system, read the plan and generate the code. DesignVeave also produces a configuration cookbook and creates some of the configuration directly in the system.

Because design and build sit in one place, each object can be traced back to the requirement that asked for it.

---

*Vinod Kumar is the founder of Xveave Technologies and has spent 26 years designing and delivering SAP solutions.*
