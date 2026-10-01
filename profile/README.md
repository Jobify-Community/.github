# Jobify Community

**Jobify** is a modern, high-precision, and robust `asyncio` task management framework for Python. We are building a high-performance ecosystem for event-driven background job scheduling.

---

## 🚀 Technical Pillars

| Feature                       | Description                                                                            |
| :---------------------------- | :------------------------------------------------------------------------------------- |
| **Zero-Polling Precision**    | Leverages native `asyncio` timers for sub-millisecond accuracy without idle CPU usage. |
| **Developer-Centric API**     | FastAPI-inspired `JobRouter`, dependency injection, and decorator-based routing.       |
| **Reliability & Persistence** | Built-in SQLite storage ensures job survival across application restarts.              |
| **Advanced Control Flow**     | Native support for middlewares, hierarchical exception handlers, and lifecycle events. |

---

## 🌐 The Ecosystem

- **[jobify](https://github.com/s3ths1/jobify):** The core framework for modern task management.
- **[jobify-db](https://github.com/Jobify-Community/jobify-db):** Database adapters for Jobify: PostgreSQL, MongoDB, and more..
- **[dishka-jobify](https://github.com/Jobify-Community/dishka-jobify)** Dishka framework integration for Jobify.
- **`jobify-distributed` (Upcoming):** Scalable, multi-worker task distribution for high-load environments.

---

## 💻 The "Jobify Way"

```python
import asyncio
from jobify import Jobify

app = Jobify()

@app.task
async def sync_data(source: str) -> None:
    print(f"Syncing from {source}...")

async def main() -> None:
    async with app:
        # Schedule with 5-second delay
        await sync_data.schedule("remote").delay(seconds=5)

        # Schedule using Cron expression (every minute)
        await sync_data.schedule("local").cron("* * * * *")

        await app.wait_all()

if __name__ == "__main__":
    asyncio.run(main())
```

---

## 🤝 Connect & Contribute

- **Main Repository:** [theseriff/jobify](https://github.com/theseriff/jobify)
- **Documentation:** [theseriff.github.io/jobify/](https://theseriff.github.io/jobify/)
- **Support:** [GitHub Issues & Discussions](https://github.com/theseriff/jobify/discussions)
- **Contribution Guide:** [CONTRIBUTING.md](https://github.com/theseriff/jobify/blob/main/CONTRIBUTING.md)

---

Built with ❤️ by the Jobify Community.
