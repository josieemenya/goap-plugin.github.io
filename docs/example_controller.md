# Example Controller

## Description

`ExampleController` is a Blueprint implementation of [`AExampleController`](API_ref/example_ct_api.md) that provides a ready-to-use AI setup for the plugin.

It includes the core components required for goal selection and planning, making it the fastest way to get an AI agent running.

This controller is recommended for:

- beginners
- Blueprint-only users
- rapid prototyping
- users unfamiliar with GOAP or Utility AI systems

---

## Why use it?

Setting up a planning-based AI architecture from scratch can be time-consuming.

`ExampleController` provides a working reference implementation with the required systems already configured, allowing you to focus on creating Goals and Actions rather than boilerplate setup.

Use it if you want to:

- get an AI agent running quickly
- learn how the plugin is structured
- prototype behaviours without writing C++
- use the plugin entirely through Blueprints

---

## Included Components

`ExampleController` includes:

- [`BlackboardComponent`](https://dev.epicgames.com/documentation/unreal-engine/API/Runtime/AIModule/UBlackboardComponent)
- [`Planner`](planner.md)
- [`Reasoner`](utility_system.md)

These components work together to:

- evaluate Goals
- generate Action plans
- execute decision-making behaviour

---

## Can I replace it?

Yes.

`ExampleController` is provided as a reference implementation and convenience starting point, not a required dependency.

Advanced users may create their own AI Controller implementations using the plugin's Planner and Reasoner systems.

If replacing it, refer to the [`AExampleController`](API_ref/example_ct_api.md) documentation for required setup and integration details.