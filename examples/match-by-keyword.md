# Example: match by keyword

## User input

```text
我想拆解一篇爆款文章
```

## Expected behavior

The skill should map the request to the closest indexed prompt by intent and return the documented match header plus the original template body.

A likely match is:

- `深度技术图文/公众号大纲拆解与生成`

If multiple prompts are similarly close, the skill should present 2–3 candidate options for confirmation.
