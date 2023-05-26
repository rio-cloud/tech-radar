# RIO Technology Radar
* [Current Radar](https://backstage.developers.rio.cloud/tech-radar)

## Purpose

The Tech Radar is a tool that should give engineering teams at RIO
guidance to pick the best technologies for their projects. It provides a
platform to share knowledge and experience in technologies, reflecting
the maturity level of each item and the decisions that led to it.

Using the Paved Road concept, where all mature technologies have a
well-documented application and reduced operational efforts. It also
reduces the learning curve by increasing the alignment, cooperation and
knowledge sharing between teams. Therefore the blips in **adopt and
fundamental represent the Paved Road** of our platform. Conversely this
means, that lifting a blip into one of those rings, it must fit our
platform.

The tech radar is a constantly evolving document, always reflecting the
latest decisions and also all experiments being conducted and their
results, where any developer at RIO is welcome to participate.

## What it’s not

As we at RIO believe in our teams to make the best decisions for RIO,
the Tech Radar is not a list of the "only" accepted technologies to be
used at RIO.

It should give an overview of the standards we agreed on and as of that
give a hint for decisions that might need further consultation. But it
should explicitly not be understood to disallow technologies not
mentioned in the Tech Radar.

# Principles

|Principle|Description|
|--|--|
|AWS first|Favor AWS platform service over managed service, over self-hosted OSS, over self-built solutions. |
|Avoid self-hosting of non managed tools| If there is a service with a sensible pricing, try to leverage this instead. Self-hosting should be the last possible option. |
|Everything as code (Automation, IsaC)| We’re focusing on our primary programming languages. These are Kotlin for Backends (especially ECS services) and TypeScript for Frontend and Lambdas at the moment. |
|High impact| It should improve overall efficiency and reduce friction, effort and impact for teams. |
|Paved Roads| Provide documentation, standardized and compatible components, components/features as a service. |
|You build it, You run it!| Everything that should become part of the Paved Road (meaning adopt of fundamental), must be operable by the teams and therefore they should be able to monitor and detect problems using the suggested tooling (e.g. Datadog, Opsgenie etc.). |
|Less opinionated decisions| Decisions are based on facts and data instead of feelings and preferences |
|Continuous feedback| Continuous feedback is gathered, when relevant, to improve collaboration and avoid blind spots and also for a less biased decision-making |
|Incremental features/experimentation | Frequent and small releases are critical to getting valuable feedback in time to have an impact in the solution conception |

# Structure

## Categories

We document our tech stacks in three categories, although we think, that
the categories are just for better overview and thus not too important.

-   Techniques
-   Languages
-   Libraries and Frameworks
-   (Managed) Services

Quoted from <https://www.thoughtworks.com/radar/faq-and-more>

> We don’t make a big deal out of the quadrants — they’re really just a
> way to break up the Radar into topic areas. We don’t think it’s
> important which quadrant a blip goes into, unlike the rings - which
> generate a lot of discussions.

## Rings (Levels)

Each technology is in one of the following Rings (Levels):

### Fundamental (former "Defaults")

**We as RIO are most experienced with these items as this are our core
techniques, tools and languages.**

They are mostly used in every team, where we share experiences and
learnings.

We need strong proof and use cases to move an item out of this level
such as reducing maintenance efforts etc.

### Use / Adopt

**Items that have been tested and are already used successfully in
production**.

When an item in this level replaces another one we keep the reference to
the outdated one.

When you are refactoring your existing services think about adopting
them.

### Trial

**Ongoing tests - in production.**

Items are being tested by a team, and the results, success or failures,
will be shared the rest of the organisation. As we do not have a
dedicated Assess ring, also planned experiments should be added to trial
in order to find other colleagues or teams that are interested in
joining the experiment.

It should not be adopted by other teams, only if in agreement with the
team responsible for the trial before. Since it may pass for multiple
breaking changes due to its immaturity, or even not being adopted.

It may replace other items.

When adding **libraries**, consider their "relevance" to the company, if they are a vital part of your code and 
business they could be added individually with their own blip, if they are more generic and used by core parts 
(e.g. code formatting, logging) or really specific to one use case (VDA files parsing), try to add a more generic
description in the "Techniques" ring and use the libraries as an example.

The library's relevance and maturity will be taken into consideration by the RIO TechRadar community when they are 
being moved into higher rings.

### Hold

**Items that have been replaced by better successors or are considered
obsolete or deprecated.**

Discouraged from broad adoption, no new applications may use it.

Trial items showed enough reasons to not be continued due to concerns
(security problems, licensing), missing integration to our default
applications (monitoring, metrics), so we do not recommend trying them
further.

When you have them in a active service, consider migrating according to
the business strategy. Possible exceptions are services considered
feature complete or in maintenance mode.

### Archive

Items that are no longer relevant for the radar but are kept for
historical purposes.

Items that were part of a trial but were not finalized or for a longer
period on hold.
