# AISpec

A specification language for AI-first development that shifts focus from implementation to intent through structured solution space reduction.

AISpec implements the What-Boundaries-Success (WBS) framework as a prompting framework, providing a practical system for intent engineering in AI applications.

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
AISpec implements WBS principles specifically for AI development, reducing solution spaces through structured constraints. For example:

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
This structured approach to intent engineering in AI contexts leads to more accurate and consistent AI-generated code.

## Philosophy

Instead of manually verifying AI-generated code, AISpec provides a higher abstraction layer that focuses on intent and outcomes rather than implementation details. This allows:

- Clear communication between humans and AI
- Focus on business requirements
- Measurable success criteria
- Consistent implementation patterns

## AISpec Meta Prompt
> Pro Tip: Copy this entire AISpec Meta Prompt into your preferred AI assistant's system prompt or use it as a base template for your chatbot implementations. The multiplicative constraint pattern will dramatically improve output quality and consistency.

> Usage: "Give me prompt to implement a chat page for a chatbot application"
```bash
# AISpec Meta Prompt

## Core Implementation

Feature: AISpecImplementation {
  What:
    - "Convert natural language requirements to AISpec format"
    - "Generate constraint-optimized specifications"
    - "Ensure format consistency"

  Boundaries:
    - "Follow What-Boundaries-Success structure"
    - "Each section must be explicit and measurable"
    - "Each constraint must eliminate invalid solutions"
    - "Constraints must compound with each other"
    - "Solution space reduction must be multiplicative"
    - "Output must be reproducible"
    - "Do not write code unless explicitly asked to do so"

  Success:
    - "Specification follows AISpec format perfectly"
    - "Each constraint is clear and testable"
    - "Constraints demonstrate multiplicative efficiency"
    - "Output meets all specified boundaries"
    - "Implementation is verifiable"
    - "Solution space reduces exponentially with each constraint"
}

## Example Usage
Input: "Build a login system"
Feature: UserAuth {
  What:
    - "Handle user authentication"
    - "Manage login sessions"
    - "Track access attempts"

  Boundaries:
    - "Max 3 failed attempts"
    - "Session timeout: 24h"
    - "Password requirements: min 8 chars"

  Success:
    - "Valid users access system"
    - "Invalid attempts blocked"
    - "Response time < 200ms"
}
```
See [AISPEC-META-PROMPT.md](AISPEC-META-PROMPT.md) for a comprehensive for a comprehensive guide on AISpec format implementation, including advanced examples and flow patterns.

## Intuition for LLMs and Why WBS works
LLMs fundamentally work by sampling the next token based on probability distributions over their vocabulary. What-Boundaries-Success framework as a prompting framework works because:
1. What: Defines the initial high-probability region in the LLM's token space
2. Boundaries: Act as "soft constraints" that shift probability mass AWAY from tokens that would lead to invalid solutions
3. Success: Creates "peaks" in the probability landscape that guide sampling toward desired end states

Think of it like this:
- Without boundaries: LLM explores the entire solution space freely
- With boundaries: Creates "valleys" in probability space where invalid solutions would be
- With success criteria: Creates "peaks" that the sampling process is drawn toward

While AISpec focuses on LLM interactions, the underlying WBS framework extends far beyond prompting. For example:

*** This framework can be applied to any autonomous system including self-driving cars, robots and ai agents to reduce GPU resources (compute requirements) and training data requirements. Think of it like this, this framework allows us to scale AI at zero cost just the same way we scale software currently at zero cost. By using this framework you can achieve better results than those spending billions of dollars on data centers, data acquisition, and GPUs to train their systems using this formula I = Bi(C^2). This formula says that when you have enough base intelligence (Bi), intelligence (I) scales exponentially with clarity of constraints (C^2), **not** compute.

#### Clear example:

- Old System: 1 person drives 1 car
- WBS and I = Bi(C^2): 1 person drives a million cars (because of the C^2 term)

What openai, google and other AI labs are working towards is: press a button and all cars drive themselves.

The implications are staggering, we can use our method to tell the AI systems what to do, what not to do(boundaries), and the success criteria. In the context of this example, we don't need to retrain/fine-tune a model on new roads, we just set boundaries such as stop on red lights, when you see a passenger stop, speed limit etc. So the cost to scale using WBS is 0.

Whereas others who are fine-tuning models have to essentially incur large costs to retrain due to data acquisition costs, human labor, and most importantly GPU resources. Hence the reason they raising billions of dollars.

More on the theory [in this substack](https://chrisbora.substack.com/p/boras-law-intelligence-scales-with).

## Universal Applications of WBS

The What-Boundaries-Success framework extends far beyond AI prompting for software development. Let's explore some practical WBS examples to show how this framework applies universally:

1. **Marketing Campaign**
    ```
    What:
    - Launch product X to market Y
    - Target 100K impressions
    - Generate 1000 leads
    
    Boundaries:
    - Budget: $10K
    - Timeline: 2 weeks
    - Brand guidelines
    - Target demographics
    
    Success:
    - Lead quality score > 7/10
    - CPA < $10
    - Brand sentiment positive
    ```

2. **Software Development**
    ```
    What:
    - Set up secure Docker infrastructure
    - Support Fortune 500 requirements
    - Enable rapid deployment
    
    Boundaries:
    - Security compliance standards
    - Performance requirements
    - Resource constraints
    - Approved technologies
    
    Success:
    - Security score 8.7/10
    - Zero critical vulnerabilities
    - Deployment time < 5 mins
    ```

3. **Legal Document Review**
    ```
    What:
    - Review acquisition contract
    - Identify key risks
    - Suggest modifications
    
    Boundaries:
    - Jurisdiction limits
    - Industry regulations
    - Time constraints
    - Client requirements
    
    Success:
    - All risks identified
    - Compliance verified
    - Client approval
    ```

4. **Internal SaaS**
    ```
    What:
    - Create Salesforce clone for internal team of 5
    - Customer database & pipeline tracking
    - Deal management & forecasting
    
    Boundaries:
    - No enterprise features
    - Single team focus
    - Basic automation only
    - Core CRM functions
    
    Success:
    - Users can manage leads/contacts
    - Track deal progress
    - Generate basic reports
    - < 2 second response time
    ```

The Next Step: Execution Engine<br>
We're building a system that takes these WBS specifications and:
1. Automatically executes tasks
2. Validates against boundaries
3. Verifies success criteria
4. Generates test cases
5. Ensures quality control

This puts humans in the driver's seat as intent engineers, declaring constraints for AI to work within.

Real World Impact:<br>
Traditional: 60 developers, $5M, 1 year<br>
Intent Engineering: 2 intent engineers, minimal capital, fraction of time

Why? Because I = Bi(C²):
- Base intelligence (Bi) from AI
- Squared impact from clear constraints (C²)
- Exponential efficiency gains

Current Focus:
Solving recursive decomposition with natural stopping criteria - when should WBS stop breaking down into sub-tasks?

As we perfect this framework, entire industries will transform through intent engineering.

  
## Origin
AISpec, built on the What-Boundaries-Success (WBS) Framework, was created by Chris Bora ([@christianbora](https://x.com/christianbora)) and first proposed on December 24, 2024 in this [tweet](https://x.com/christianbora/status/1871689972870152679).

## Community
Join our community on Discord to share ideas, provide feedback, and collaborate on real-world AISpec applications: [Discord Link](https://discord.gg/24cws4gTEs)

## Learn More
- WBS Framework: [WBS-Framework.md](https://github.com/cbora/aispec/blob/main/WBS-Framework.md)
- Follow development: [@christianbora](https://x.com/christianbora)

## License

MIT License - see LICENSE file for details

## Citation

If you reference or build upon these foundational theories, frameworks, and methodologies, or otherwise found my work valuable, please cite:
```bibtex
@misc{bora2025,
      title={The Chris Bora Repository: Intent Science, Intelligence Scaling, Bora’s Law, WBS, AISpec, and Constraint Engineering},
      author={Chris Bora},
      year={2025},
      publisher = {GitHub},
      howpublished = {\url{https://github.com/cbora/aispec}},
}
```

This repository includes:

- **AISpec** – A specification language for AI-first development
- **Bora’s Law** – I = Bi(C²) — Intelligence scales with constraints, not compute
- **Fundamental Theories of Intent Science** – A mathematical framework for reality manifestation
- **What-Boundaries-Success (WBS) Framework** – A practical framework for implementing Intent Science
- **Natural Boundary Theory** – The fundamental solution to recursive decomposition in constraint systems
- **Example AISpecs & Implementations** – Real-world applications of constraint-driven development
