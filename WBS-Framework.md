# The What-Boundaries-Success Framework
## Introduction


Complex systems, particularly those driven by artificial intelligence, present a fundamental challenge: how do we ensure reliable, predictable behavior while maintaining flexibility? Traditional approaches attempt to validate outputs after generation, a strategy that becomes increasingly untenable as systems grow in complexity and capability.

Consider the trajectory of system development:

- Past: Manual programming with fixed rules
- Present: AI systems with probabilistic behavior
- Future: Constrained AI with deterministic boundaries

It’s in this “future” space that the What-Boundaries-Success (WBS) Framework provides a robust solution, ensuring predictable outputs by design rather than by reactive checks.

My journey to understanding system constraints began unexpectedly while working on neutrino detection systems at the South Pole, where precise boundary conditions determined the difference between signal and noise. Later, while working on search and knowledge recommendation systems at Meta, I observed how structured queries dramatically reduced solution spaces compared to keyword searches. This insight deepened while developing AI applications, where I noticed language models produced dramatically better results after multiple conversation turns, suggesting they needed complete context to generate reliable outputs. These observations led me to question the fundamental nature of AI system control.

The What-Boundaries-Success (WBS) Framework emerged from observing how prompting techniques like Chain of Thought, Tree of Thoughts, Reflection, and self-consistency attempt to improve AI outputs through post-generation verification. Working with these methods revealed their limitations - they were trying to verify outputs after generation rather than constraining the generation process itself. Drawing from my background in computer science and graph theory, I began to see how solution spaces could be constrained before generation, similar to how physical constraints guide particle behavior. This insight evolved into a systematic approach for reducing solution spaces through explicit boundary definition.

Initial validation came quickly through applications in financial trading and code generation, where explicit constraint definition consistently produced reliable results. Trading strategies became predictable when bounded by clear risk parameters, while code generation became deterministic within well-defined technical constraints. These successes revealed another insight: existing prompting techniques like Chain of Thought, Tree of Thoughts, and Reflection could be understood as methods for efficiently searching within constrained solution spaces. Rather than replacing these techniques, the WBS Framework provides the fundamental structure within which they operate most effectively - guiding the search toward success criteria through well-defined boundaries.

The framework provides a structured approach to controlling complex systems through three interlocking components: clear specification of intent (What), explicit definition of constraints (Boundaries), and measurable validation criteria (Success). Rather than hoping a system produces correct outputs and verifying afterward, WBS enables us to define spaces within which all outputs must be correct.

## Framework Fundamentals

The WBS Framework consists of three fundamental components that work together to define and control system behavior. Each component serves a distinct purpose while maintaining clear relationships with the others.

The "What" component defines intent - not just desired outcomes, but the essential nature of what we're trying to achieve. Unlike traditional specifications that focus on implementation details, "What" captures the fundamental purpose. For example, rather than specifying how to validate user input, we define what valid input means in our context.

The "Boundaries" component transforms infinite possibility spaces into manageable domains. These aren't mere guidelines or preferences - they are hard constraints that structurally eliminate invalid solutions. This transforms our problem from searching vast spaces to operating within well-defined bounds. The power lies not in checking boundaries after the fact, but in making certain outcomes structurally impossible.

The "Success" component provides measurable criteria that define valid outcomes. This differs fundamentally from traditional success metrics by being both necessary and sufficient - any output meeting these criteria is valid, and any valid output must meet these criteria. This creates a clear contract between specification and implementation.

The interaction between these components creates a framework that is both rigorous and practical:

- "What" defines the space of possible solutions
- "Boundaries" constrain this space to valid regions
- "Success" verifies we've reached our target

## Theoretical Foundation

The power of the WBS Framework rests on fundamental principles of system control and constraint theory. When we define a problem space, we're essentially mapping out all possible states our system could reach. Without proper constraints, this space is effectively infinite, making reliable control impossible.

Consider a system generating text. Without constraints, it can produce any sequence of characters - an infinite space of possibilities. Traditional approaches attempt to navigate this space through sophisticated prompting or post-generation validation. The WBS Framework instead reshapes the space itself.

This reshaping occurs through what we might call "constructive constraint" - the systematic reduction of possibility spaces through well-defined boundaries. Unlike filtering, which removes invalid outputs after generation, constructive constraint makes invalid outputs structurally impossible.

The mathematical beauty of this approach lies in its deterministic nature. Given the same What-Boundaries-Success specification, a properly constrained system will always operate within the same reduced solution space. This transforms probabilistic systems into deterministic ones.

The practical implications of this theoretical foundation are profound. By defining clear boundaries before generation or execution, we create systems that are reliable by construction rather than validation. This shifts the burden of correctness from testing to specification - a fundamentally more robust approach.

When applied to AI systems, this framework provides what traditional approaches have struggled to achieve: predictable behavior without sacrificing flexibility. The system remains free to innovate within its bounded space while structural constraints ensure it cannot violate critical requirements.


## Applications

The true power of the WBS Framework reveals itself in practical applications. While initially developed through experiences with AI systems, its principles extend naturally to any domain requiring controlled yet flexible behavior.

Consider AI code generation. Traditional approaches generate code and then verify its correctness. With WBS, we instead define:

- What: The code's intended functionality
- Boundaries: Performance, security, and architectural constraints
- Success: Specific, measurable acceptance criteria

This transforms code generation from a probabilistic process into a deterministic one within defined constraints.

In decision-making systems, particularly those handling financial analysis or risk assessment, WBS provides a rigorous framework for controlling outcomes. Rather than hoping an AI makes appropriate decisions, we define explicit boundaries within which all decisions must fall. This is particularly powerful in trading scenarios, where clear risk parameters and success criteria are essential.

Perhaps most critically, WBS offers a path forward for autonomous system development. Current approaches struggle with the infinite variety of real-world situations. By defining clear boundaries and success criteria, we can create systems that are provably safe within their operating parameters while maintaining the flexibility to handle novel situations.

## Case Studies

### Code Generation with WBS

Consider a real-world example of generating an authentication system:

```bash
Feature: Authentication {
  What:
    - "Handle user login flow"
    - "Manage session state"
    - "Control access rights"
    
  Boundaries:
    - "Password hashing required"
    - "Rate limiting enforced"
    - "Session timeout maximum 24h"
    
  Success:
    - "Valid users gain access"
    - "Invalid attempts blocked"
    - "All security tests pass"
}
```

### Trading Decision Framework

The application of WBS to trading decisions demonstrates its power in risk control:

```bash
Feature: TradingDecision {
  What:
    - "Analyze market conditions"
    - "Identify entry points"
    - "Define position sizing"
    
  Boundaries:
    - "Maximum 2% risk per trade"
    - "Limited to specific instruments"
    - "Pre-defined timeframes"
    
  Success:
    - "Clear profit targets"
    - "Defined risk/reward ratio"
    - "Measurable entry precision"
}
```


These cases demonstrate how WBS transforms complex, open-ended problems into well-defined solution spaces. The framework doesn't limit creativity - it channels it productively within safe, reliable bounds.


## Future Implications

The WBS Framework is ready for implementation today. Individuals and small teams building AI workflows often rely on reactive testing and validation to catch problems after they emerge. WBS changes this dynamic by making correct behavior intrinsic to a project’s design. Rather than hoping AI systems behave correctly or attempting to verify outputs after generation, WBS provides a systematic approach to guaranteeing correct behavior by design.

Consider current AI development challenges:

- **Code Generation**
    - **Before (Common Pain Point)**: The generated code is incomplete or breaks easily because the AI isn’t fully constrained by user requirements. This leads to code  that doesn’t meet functional requirements, leading to errors, security flaws, or off-spec implementations. As a result developers waste many hours debugging the generated code.
    - **After (WBS Solution)**: By clearly defining What (intended functionality), Boundaries (e.g., resource constraints, security rules, coding standards, design patterns, programming language, etc.), and Success (e.g., tests must pass, performance must meet a threshold), a single developer or small team can quickly achieve deterministic, higher-quality code outputs. Early tests show fewer bugs, less rework, and more confidence in AI-generated components. In one pilot, developers reported spending 30% less time debugging on the first pass once WBS constraints were defined.

- **Trading Systems**
    - **Before (Common Pain Point)**: AI models often generate off-target strategies that don’t match user-defined preferences or risk tolerances. They also might not consider subtle constraints (like maximum position sizes, timeframe preferences, user-defined risk tolerances, capital constraints, etc.)—-leading to ideas that are simply unusable.
    - **After (WBS Solution)**: By specifying precisely what kinds of trades or risk levels are allowable, plus success metrics (e.g., minimum Sharpe ratio, acceptable drawdowns), even an individual trader can ensure the AI only suggests strategies that fit their exact criteria. This bottom-up approach doesn’t require an organizational mandate—just the will to define clear constraints up front making it simple for a single analyst to apply WBS constraints and validate outputs more reliably--no executive sign-off required.

These scenarios illustrate how WBS shifts AI from a validation problem to a design solution. When constraints are explicitly defined, AI systems naturally stay within safe, desired parameters—before code is even written or strategies are proposed.

Individuals and small teams can adopt WBS without waiting for enterprise-wide directives.

Concrete steps include:

- **Define** WBS specifications for current projects—-pinpoint the What, Boundaries, and Success metrics
- **Incorporate** constraints in new AI initiatives—integrate them into your development pipelines
- **Train** team members through cross-functional workshops, ensuring domain experts and engineers align on constraints
- **Establish** and share reusable constraint libraries for common scenarios (data privacy, security, risk models)

Because each of these steps can be done at a small scale, WBS offers a **low-friction entry point**. Once a team sees improvement in code quality or trading strategy alignment, it becomes a natural next step to scale across larger efforts.

## Conclusion

The WBS Framework emerged from practical challenges in AI development but provides immediate solutions to fundamental problems in system control. Its power lies not in future possibilities but in today's applications - whether in code generation, trading systems, or autonomous systems.

Individuals and teams implementing WBS today gain:

- **Predictable AI behavior** through built-in constraints
- **Reduced validation costs** by shifting correctness into the design phase
- **Faster development cycles** with fewer post-hoc fixes
- **Intrinsic safety guarantees** that foster trust and regulatory compliance

In short, WBS helps you build safer, more reliable systems **right now**, giving you peace of mind and a solid foundation to grow—whether you’re a solo developer testing AI code generation or a small trading desk refining trading strategies. By starting small and proving its value, WBS naturally scales to larger organizational contexts, ultimately transforming how we approach AI design in the future.

Every individual or team implementing WBS creates a proof point for constraint-based development, gradually shifting the industry from hope-based validation to systematic control. Just as test-driven development spread from individual developers to become an industry standard, WBS can transform how we approach AI system development - one implementation at a time.

## Contributing

This framework is open for discussion, refinement, and expansion. As new applications emerge and new challenges arise, the WBS Framework will evolve while maintaining its core principles:

- Clear intent specification
- Explicit boundary definition
- Measurable success criteria

Join our community on [Discord](https://discord.gg/24cws4gTEs) to share ideas, provide feedback, and collaborate on real-world WBS applications. [Click here to join](https://discord.gg/24cws4gTEs)

## Resources

The [AISpec](https://github.com/cbora/aispec) implementation provides a concrete example of WBS principles in action. By examining how AISpec uses these concepts to control AI outputs, developers can better understand how to apply these principles to their own domains.

