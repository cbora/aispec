# Comments in AISpec

We've carefully considered the role and types of comments in AISpec specifications. After analysis, we concluded that only human-focused comments are necessary.

## Comment Format

```bash
<----- This is a comment for HUMAN USE ONLY:
[Your comments here]
----->
```

The specific phrasing "This is a comment for HUMAN USE ONLY:" is intentional and should be used consistently. This clear, natural language instruction helps LLMs understand to ignore these comments while remaining readable for humans.


## Types of Comments Considered


1. **Human-Only Comments** ✅

    * Purpose: Team communication, notes, TODOs, review requirements
    * Implementation: Using clear delimiters

        ```bash
        <----- This is a comment for HUMAN USE ONLY:
        This section needs security review
        TODO: Add rate limiting
        ----->
        ```

2. **LLM-Only Comments** ❌

    * Initially considered for special processing instructions or LLM context
    * Concluded: Any information needed by LLMs should be part of the formal spec structure (What/Boundaries/Success)


3. **Dual LLM-Human Comments** ❌

    * Initially considered for shared context
    * Concluded: This information belongs in the formal spec structure
    * The AISpec format itself serves this purpose



## Reasoning

If information is relevant for the LLM's understanding or processing, it should be formalized in the spec structure
The What-Boundaries-Success format already provides clear communication for both humans and LLMs
Human-only comments serve a distinct purpose for team communication and development notes

## Examples
See `comment-example.aispec` for implementation examples.
