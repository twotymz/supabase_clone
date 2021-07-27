# Mock supabase.io

Minimal project to get a [supabase.io](http://supabase.io) back-end working locally mostly derived from their docker files but with some QOL mods by me.

## Usage
1. Modify `.env` if needed.
2. `docker-compose -f docker-compose.yml up`

If everything works successfully then all the services will be accessible on `localhost` at the ports specified in `.env`.

The supabase js client ([supabase-js](https://github.com/supabase/supabase-js)) can also be used for local front-end development by specifying `http://localhost:{KONG_PORT}` and `{SUPABASE_ANON_KEY}` in `createClient`.

```javascript
import { createClient } from '@supabase/supabase-js'

// Create a single supabase client for interacting with your database
const supabase = createClient('http://localhost:60005', 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJyb2xlIjoiYW5vbiIsImlhdCI6MTYyNDM4MDYzNCwiZXhwIjoxOTM5OTU2NjM0fQ.SDH7wXuJ0WMRpgvSLIolzqI8wn7XAdl8p5niE8y-PYw')
```
