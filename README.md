# AISpec

A specification language for AI-first development that shifts focus from implementation to intent through structured solution space reduction.

Built on the What-Boundaries-Success (WBS) Framework, AISpec provides a practical implementation of systematic constraint engineering for AI systems.

## Overview

AISpec is a declarative format for defining software features in a way that's both human-readable and AI-parseable. It focuses on three key aspects:
1. Declaring WHAT we want
2. Setting BOUNDARIES
3. Defining SUCCESS CRITERIA

## Core Format

```
Feature: Name {
  What:
    - "Clear action items"
    - "Each one executable"
    
  Boundaries:
    - "Performance limits"
    - "Resource constraints"
    - "Business rules"
    
  Success:
    - "Measurable outcomes"
    - "Clear metrics"
    - "Expected behavior"
}
```

## Example

```
Feature: UserAuth {
  What:
    - "Handle user login"
    - "Issue JWT token"
    - "Track attempts"

  Boundaries:
    - "Max 5 attempts/hour"
    - "Token expires 24h"
    - "Passwords hashed"

  Success:
    - "Valid users login"
    - "Invalid blocked"
    - "Response < 200ms"
}
```

## Extended Format

For more complex features, the format can be extended with additional sections:

```
Feature: Name {
  # Core sections as above, plus:
  
  Technical:
    framework: "specified-framework"
    database: "database-type"
    patterns: ["design-patterns"]
    
  Dependencies:
    required: ["necessary-packages"]
    optional: ["nice-to-have-packages"]
    
  Security:
    auth: "requirements"
    encryption: "needs"
    rate_limits: "constraints"
}
```

## Examples
See the `examples/` directory for:
- Basic usage patterns
- Advanced features including Flow specifications
- Real-world implementation scenarios

## Theory
AISpec's effectiveness comes from its ability to reduce the solution space through structured constraints. For example:

Traditional prompt: 
```bash
"Write authentication code"
# Solution space: 1000s of possible implementations
```
AISpec format:
```bash
Feature: Auth {
  What: [specific criteria]
  Boundaries: [clear constraints]
  Success: [measurable outcomes]
}
# Solution space: Reduced to few viable implementations
```
This structured reduction leads to more accurate and consistent AI-generated code.

## Philosophy

Instead of manually verifying AI-generated code, AISpec provides a higher abstraction layer that focuses on intent and outcomes rather than implementation details. This allows:

- Clear communication between humans and AI
- Focus on business requirements
- Measurable success criteria
- Consistent implementation patterns

## Origin
AISpec, built on the What-Boundaries-Success (WBS) Framework, was created by Chris Bora ([@chrisbora_](https://twitter.com/chrisbora_)) and first proposed on December 24, 2024 in this [tweet](https://x.com/chrisbora_/status/1871689972870152679).

## Community
Join our community on Discord to share ideas, provide feedback, and collaborate on real-world AISpec applications: [Discord Link](https://discord.gg/24cws4gTEs)

## Learn More
- WBS Framework: [WBS-Framework.md](https://github.com/cbora/aispec/blob/main/WBS-Framework.md)
- Follow development: [@chrisbora_](https://twitter.com/chrisbora_)

## License

MIT License - see LICENSE file for details
