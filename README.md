# PureLabel

AI-powered food ingredient scanner. Scan any packaged food label and instantly understand what's in your food.

## Routes

TanStack Start uses **file-based routing**. Every `.tsx` file in `src/routes/` is a route.

| File | URL |
| --- | --- |
| `index.tsx` | `/` |
| `auth.tsx` | `/auth` |
| `scan.tsx` | `/scan` |
| `history.tsx` | `/history` |
| `products.$id.tsx` | `/products/:id` |
| `account.tsx` | `/account` |
| `preferences.tsx` | `/preferences` |

`routeTree.gen.ts` is auto-generated. Don't edit it by hand.

## Setup

### 1. Environment Variables

Copy `env` to `.env` and fill in your values:

```
SUPABASE_URL=...
SUPABASE_PUBLISHABLE_KEY=...
SUPABASE_SERVICE_ROLE_KEY=...   # server-side only
AI_API_KEY=...                  # OpenRouter key — see below
```

### 2. AI API (OpenRouter)

This app uses [OpenRouter](https://openrouter.ai) as the AI gateway with `google/gemini-2.5-flash`.

1. Sign up at https://openrouter.ai
2. Create an API key
3. Set it as `AI_API_KEY` in your `.env`

### 3. Google OAuth

To enable "Continue with Google" with your own branding:

1. Go to [Google Cloud Console](https://console.cloud.google.com) → APIs & Services → OAuth consent screen
2. Create or update the app with your name **PureLabel** and logo
3. Create OAuth 2.0 credentials (Web Application)
4. In Supabase → Authentication → Providers → Google, enter your Client ID and Secret
5. Add your domain to the authorized redirect URIs

### 4. Custom Email (Optional)

To send emails from `noreply@yourdomain.com` instead of Supabase's default:

1. Set up [Resend](https://resend.com) with your domain
2. In Supabase → Authentication → Email → SMTP, enter your Resend SMTP credentials

## Development

```bash
bun install
bun dev
```

## Build

```bash
bun build
```
