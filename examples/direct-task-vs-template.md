# Example: direct task vs template distribution

## User input

```text
这是文章内容，帮我直接总结
```

## Expected behavior

The skill should **not** output a prompt template.

Instead, it should treat the request as a direct task because the user has already supplied source material and asked for execution.

## Why this matters

This is a core boundary of the skill:

- template retrieval when the user asks for a prompt
- direct execution when the user already provided material and wants the work done
