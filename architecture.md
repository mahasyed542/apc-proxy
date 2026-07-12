[Agent App] ───(POST /v1/chat/completions)───> [ YOUR PROXY ] ───> [ LLM Origin (OpenAI) ]
                                                    │
                                         [ Payload Interceptor ]
                                                    │
                                                    ▼
                                         [ State Log Store (JSON) ]


{
  "trace_id": "agent_session_9x8f2c",
  "timestamp": "2026-07-12T23:15:00Z",
  "request": {
    "model": "o1-preview",
    "temperature": 0.0,
    "messages": [
      {
        "role": "system",
        "content": "You are an autonomous triage agent. Step 1: List issues. Step 2: Assign team."
      },
      {
        "role": "user",
        "content": "Scan the repo for memory leaks and assign to infra."
      }
    ]
  },
  "response": {
    "id": "chatcmpl-12345",
    "choices": [
      {
        "message": {
          "role": "assistant",
          "content": "Plan: I will first call 'list_github_issues' with state='open', then filter for 'leak', and match to the 'infrastructure' roster."
        }
      }
    ],
    "usage": {
      "prompt_tokens": 1250,
      "completion_tokens": 850,
      "total_tokens": 2100
    },
    "duration_ms": 4210
  }
}
