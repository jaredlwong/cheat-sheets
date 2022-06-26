# Named Capture Groups
https://github.com/tc39/proposal-regexp-named-groups

```typescript
const serviceNameRe = /service:(?<service>.+)/
const match = serviceNameRe.exec(task.group!)!
match.groups!['service']
```
