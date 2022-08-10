# Middleware
Edge Middleware Library for Hono and Itty Router

- Request metadata enrichment
- JWT Authentication
- API Key Authentication
- OAuth & Social Login
- Rate Limiting
- Crash Reporting
- Logging
- Performance Measurement

The pattern for Hono Middleware is:

```
export const poweredBy = () => {
  return async (c: Context, next: Next) => {
    await next()
    c.res.headers.append('X-Powered-By', 'Hono')
  }
}
```

The pattern for Itty Router middleware is:
```
const requireUser = request => {
  if (!request.user) {
    return new Response('Not Authenticated', { status: 401 })
  }
}
```
