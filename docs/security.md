# Ninolex Security Practices

## API Security

### Authentication
- API key authentication for programmatic access
- Keys scoped to specific operations

### Rate Limiting
- Requests per minute based on tier
- Burst protection

### Data Privacy
- No PII in pronunciation data (linguistic only)
- Request logging for debugging (no sensitive content)

## Infrastructure

- All communication over HTTPS
- Supabase handles database security
- Modal handles serverless isolation
