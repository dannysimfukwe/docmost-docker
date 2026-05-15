# Docmost Docker

Deploy a modern collaborative wiki and documentation platform on [42helv.com](https://42helv.com).

## Features

- **One-Click Deploy** - Deploy directly from 42helv.com templates
- **PostgreSQL Database** - Automatically provisioned and configured
- **Redis Cache** - Built-in caching for performance
- **Real-time Collaboration** - Multiple users can edit simultaneously
- **SSL Ready** - Works with 42helv.com automatic SSL

## Quick Start

### Deploy on 42helv.com

1. Sign up at [42helv.com](https://42helv.com)
2. Go to **Services** → **Create New**
3. Select the **Docmost** template
4. Configure your site and deploy

Your Docmost wiki will be available at `https://your-site.42helv.com/`

### Initial Setup

After deployment, access your Docmost wiki:
- **Wiki URL**: `https://your-site.42helv.com/`
- Create your admin account on first visit
- Start building your documentation

## Configuration

The following environment variables are available:

| Variable | Default | Description |
|----------|---------|-------------|
| `APP_URL` | (auto) | Application URL (your subdomain) |
| `APP_SECRET` | (auto) | Secret key for sessions |
| `POSTGRES_PASSWORD` | (auto) | Database password |
| `REDIS_URL` | (auto) | Redis connection string |

## Local Development

```bash
# Clone the repository
git clone https://github.com/dannysimfukwe/docmost-docker.git
cd docmost-docker

# Copy environment file
cp .env.example .env

# Start with Docker Compose
docker-compose up -d

# Access Docmost at http://localhost:80
```

## Architecture

```
┌─────────────────────────────────────────────────────────┐
│              Docmost (Port 80)                          │
│         (Collaborative Wiki Platform)                   │
└──────────────────────────┬──────────────────────────────┘
                           │
                           ▼
┌─────────────────────────────────────────────────────────┐
│                   PostgreSQL                            │
│                (content database)                       │
└──────────────────────────┬──────────────────────────────┘
                           │
                           ▼
┌─────────────────────────────────────────────────────────┐
│                     Redis                               │
│              (caching & sessions)                       │
└─────────────────────────────────────────────────────────┘
```

## Tech Stack

- [Docmost](https://docmost.com/) - Modern collaborative wiki
- PostgreSQL - Primary database
- Redis - Caching and session storage
- Docker - Containerization

## Features

- **Real-time Editing** - Multiple users can edit pages simultaneously
- **Comments** - Add comments to any page
- **Version History** - Track all changes with full history
- **Markdown Support** - Write in Markdown with live preview
- **Search** - Fast full-text search across all content
- **Permissions** - Granular access control for teams
- **Attachments** - Upload and manage files

## Security Notes

1. **Strong APP_SECRET** - Use a long random secret (auto-generated on 42helv.com)
2. **SSL enabled** - Automatic HTTPS via 42helv.com
3. **Access control** - Configure team permissions appropriately
4. **Regular backups** - Export your documentation regularly

## Troubleshooting

### Can't access the wiki?
Verify the container is running: `docker ps`

### Database connection issues?
Check that PostgreSQL is accessible and `POSTGRES_PASSWORD` is correct.

### Need to reset?
Delete all volumes and redeploy from 42helv.com.

## License

MIT License - Deploy freely on 42helv.com or your own infrastructure.

---

Built with ❤️ on [42helv.com](https://42helv.com)
