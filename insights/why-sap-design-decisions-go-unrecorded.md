---
title: "Why SAP design decisions go unrecorded, and what it costs later"
seo_title: "Why SAP Design Decisions Go Unrecorded | Xveave"
description: "SAP projects record what was configured, rarely why. What a review of four design documents showed, what the gap costs, and how to close it."
slug: why-sap-design-decisions-go-unrecorded
date: 2026-11-21
author: Vinod Kumar
product: DesignVeave
---

# Why SAP design decisions go unrecorded, and what it costs later

Most SAP projects keep a careful record of what was configured and built, and almost no record of why. The decisions are made, usually well, in workshops. Then they dissolve into solution text, and the reasoning leaves with the people who were in the room. The cost arrives later, when a change request, a rollout or an audit forces someone to work out what was decided and whether it was deliberate.

## How do we know decisions go unrecorded?

We recently reviewed four process design documents from an SAP S/4HANA program. Each followed the same template, and each had a section called “Key decisions” near the end.

All four tables were empty.

The decisions existed. Reading the solution design line by line, we found 45 of them: which order types are credit-checked, where ownership of goods passes between two companies, whether a count needs a second approval. They were written as statements of how the system would work, in the middle of paragraphs about configuration.

Of those 45, 20 gave no reason anywhere in the document. Two were still open: the document described the alternatives and chose neither. And in one case, two documents stated different rules for the same intercompany price, with nothing to say which had been agreed.

## Why does it happen?

Nobody decides to leave the reasoning out. It follows from how design documents get written.

**The table comes last.** A decisions section at the end of a template is filled in after everything else, which in practice means under deadline, or never.

**Workshops produce outcomes.** Minutes record that the rush order type will only confirm against stock on hand. They rarely record that the alternative was discussed and why it lost.

**The solution text feels sufficient.** Once the design says what the system does, writing the decision out separately looks like duplication.

**The reason is obvious at the time.** Everyone in the workshop knows why. Two years later, half of them have moved on.

**Some decisions have no owner.** A rule that spans sales, procurement and finance belongs to no single document, so each one restates it slightly differently.

## What counts as a decision?

This turned out to matter more than we expected. Our first pass found 56 decisions. On a second look, 11 of them were descriptions of mechanism, and they were crowding out the real ones.

A decision has an alternative with a different business outcome. A useful test is to finish the sentence with “rather than…”. Compare two statements from the same paragraph:

- Shipping and duty costs are charged on to the receiving company.
- Those costs are captured in the delivery’s pricing and copied into the invoice.

The first is a decision. The costs could have been absorbed by the sender, and someone in finance had to agree that they would not be. The second describes how the system carries the decision out. It belongs in the solution design.

When the two are mixed, the decision list fills with configuration notes, and process owners stop reading it.

## What does it cost later?

**Change requests slow down.** Before changing a setting, someone has to establish whether it was chosen or simply never questioned. Without a record, the safe assumption is that it was deliberate, and the change waits while people are tracked down.

**Rollouts reopen everything.** A new plant or country should start from what the first site decided. A decision with its reason attached can be confirmed in a minute. A decision without one becomes a workshop, because nobody can say why it was the recommendation.

**Contradictions go unnoticed.** When two documents state different rules for the same thing, the conflict surfaces in testing, where it is expensive.

**Knowledge leaves with people.** Consultants roll off and employees change roles. What they knew about why the system works as it does was never anyone’s deliverable.

## What should a decision record contain?

Very little, which is why it is achievable:

1. **The decision, in one sentence**, stating only what was chosen.
2. **The reason**, in the words used at the time. If none was given, say so plainly. An honest gap is more useful than a reason invented afterward.
3. **Its scope**: the process it applies to, and any variant, such as intercompany only.
4. **Its status**: proposed, open or confirmed. An open decision should stay visibly open until someone chooses.
5. **The requirements it answers**, so a change to either can find the other.

## How do you start on a system that is already live?

You do not need to reconstruct everything. Three steps cover most of the value.

**Mine the documents you have.** The decisions are in the solution text. Pull them out, apply the “rather than” test, and list them.

**Mark the ones without a reason, and ask.** This is the urgent part. The people who remember are still reachable today. In our review, two reasons that looked missing were in the documents after all, stated once in a different section from the decision. The rest needed a person.

**Record new decisions when they are made.** A change request is the natural moment. Whoever approves the change states what was chosen and why, once, in the same place as the design it changes.

## Where DesignVeave fits

DesignVeave holds each decision as a record of its own, linked to the requirements it answers and the process it belongs to, with its reason and status. A change to a requirement can then find the decisions that depend on it, and a rollout starts from decisions that explain themselves.

The principle works without the tool. If you take one thing from this: the next time a design workshop settles something, write down what the alternative was.

---

*Vinod Kumar is the founder of Xveave Technologies and has spent 26 years designing and delivering SAP solutions.*
