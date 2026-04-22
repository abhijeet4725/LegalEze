# LegalEze Backend

> AI-powered legal document management system with semantic search capabilities.

---

## Prerequisites

Make sure you have the following installed before getting started:

- Python 3.9+
- pip
- Redis (running locally or via a remote URL)
- Ollama (for local AI model inference)

---

## Quick Start

### 1. Clone & Navigate

```bash
cd legaleze
```

### 2. Create a Virtual Environment

```powershell
python -m venv venv
.\venv\Scripts\activate        # Windows
# source venv/bin/activate     # macOS / Linux
```

### 3. Install Dependencies

```bash
python -m pip install -r requirements.txt
```

### 4. Configure Environment Variables

Copy the example env file and fill in your values:

```bash
cp .env.example .env
```

Open `.env` and update the following:

| Variable         | Description                              | Example                              |
|------------------|------------------------------------------|--------------------------------------|
| `DATABASE_URL`   | PostgreSQL connection string             | `postgresql://user:pass@localhost/db`|
| `REDIS_URL`      | Redis connection string                  | `redis://localhost:6379`             |
| `OLLAMA_BASE_URL`| Base URL for your Ollama instance        | `http://localhost:11434`             |

### 5. Run the Server

```bash
python run.py
```

The server will start at `http://localhost:5000`.

---

## API Documentation

Interactive API docs are available via Swagger UI once the server is running:

```
http://localhost:5000/apidocs
```

---

## Project Structure

```
legaleze/
├── run.py              # App entry point
├── requirements.txt    # Python dependencies
├── .env.example        # Environment variable template
└── app/
    ├── config/         # App configuration
    ├── ingestion/      # Document parsing & chunking
    ├── embedding/      # Vector embedding logic
    ├── repository/     # Database access layer
    ├── service/        # Core RAG orchestration
    └── controller/     # REST API endpoints
```

---

## Troubleshooting

**Virtual environment not activating?**
Make sure you're using PowerShell (not CMD) on Windows, or use `source venv/bin/activate` on macOS/Linux.

**Can't connect to Redis or Ollama?**
Verify both services are running before starting the server. Check your `.env` values match the running service addresses.
