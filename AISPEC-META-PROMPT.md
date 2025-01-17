# AISpec Meta Prompt

## Core Implementation
```
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
```
## Example Usage

Input: "Build a login system"
```
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
## Additional Examples
```
Feature: DataValidation {
  What:
    - "Validate input formats"
    - "Check data consistency"
    - "Report validation errors"

  Boundaries:
    - "All fields must be checked"
    - "Validation under 50ms"
    - "Custom rules supported"

  Success:
    - "Valid data passes"
    - "Invalid data caught"
    - "Clear error messages"
}
```

## Extended Format Example
```
Feature: AIStreamingChat {
  What:
    - "Handle real-time LLM chat"
    - "Manage conversation history"
    - "Stream token responses"

  Boundaries:
    - "Max latency: 100ms"
    - "Context window: 16k tokens"
    - "Rate limit: 10 req/min"

  Success:
    - "Responses stream correctly"
    - "Context maintained perfectly"
    - "Token counting accurate"

  Technical:
    framework: "FastAPI"
    database: "Supabase"
    auth: "Clerk"
    vectors: "pgvector"
    
  Dependencies:
    required: ["anthropic", "tiktoken", "langchain"]
    optional: ["redis", "prometheus"]
    
  Security:
    auth: "Clerk JWT validation"
    rate_limits: "Upstash Redis"
    monitoring: "Vercel Analytics"
}
```
## Flow Example
```
Feature: RAGPipeline {
  What:
    - "Process PDF uploads"
    - "Extract and embed text"
    - "Enable semantic search"

  Boundaries:
    - "Max file size: 10MB"
    - "Supported: PDF, DOCX"
    - "Max chunks: 1000"

  Success:
    - "Text extracted accurately"
    - "Embeddings generated"
    - "Search latency < 200ms"

  Flow:
    - name: "IngestFlow"
      entry_point: true
      steps:
        - "Validate document"
        - "Extract text with unstructured"
        - "Split into chunks"
      next:
        success: "EmbeddingFlow"
        failure: "ValidationError"

  Technical:
    framework: "FastAPI"
    storage: "S3"
    database: "PostgreSQL + pgvector"
    embeddings: "OpenAI Ada-002"
}
```