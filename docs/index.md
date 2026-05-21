# Welcome to the GOAP Plugin Documentation Page

## Overview

This plugin provides a modular AI framework for Unreal Engine combining Utility AI goal scoring selection with GOAP planing.

It is designed for both designers and developers who want AI agents capable of choosing meaningful goals and dynamically constructing action sequences to achieve them.

The Plugin is build around two Primary Systems : 

- [`Utility Reasoner`](utility_system.md)

- [`GOAP Planner`](planner.md)

---

## Extensibility

The system is designed to be extended in Blueprints or C++.

You can create custom:

- Goals
- Actions
- utility scoring logic
- world state synchronisation
- controller implementations

The included [`ExampleController`](example_controller.md) provides a working reference implementation, but custom controllers are fully supported.

---


## Quickstart

[Getting Started](getting_started.md)

