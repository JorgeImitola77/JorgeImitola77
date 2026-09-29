## Jorge Imitola

Final-semester software engineering student in Colombia, looking for my first
role as a backend or full-stack engineer.

---

### What I've built

**[installment_planner](https://github.com/JorgeImitola77/installment_planner)** — Go · PostgreSQL · React · TypeScript · Docker

A service that splits a purchase into interest-free installments and tracks the
payments. I built it to learn, but the parts I spent the most time on were the
ones that are easy to get wrong:

- Money is stored and calculated in **cents as integers**, never floats. The
  remainder of an uneven split is distributed deterministically instead of
  being rounded away.
- A plan and its installments are written in **one transaction**, so a partial
  plan can never exist in the database.
- Paying an installment twice concurrently is prevented **at the database
  level**, with a partial unique index — not just with an `if` in the handler.
- The business rules live in a pure package with no SQL and no HTTP, so they're
  tested without a container running. `internal/storage` is the only package
  that writes SQL; `api/client.ts` is the only module that calls `fetch`.

8 Go test files, 7 frontend test files, 100% line coverage on the frontend.
The README explains the reasoning behind each decision, including the schema.

**[ms-app](https://github.com/JorgeImitola77/ms-app)** — Python · FastAPI · PostgreSQL · React · Vite · Tailwind
A full-stack app with a FastAPI backend and workflow automation through n8n.

**[Edge-AI---OCR-Demo](https://github.com/JorgeImitola77/Edge-AI---OCR-Demo)** — C++ · Dart
OCR running on-device instead of on a server, to keep latency low and the data local.

**[sezzle-calculator](https://github.com/JorgeImitola77/sezzle-calculator)** — TypeScript
A small installment calculator. It's where the planner above started.

---

### Tools I work with

**Languages:** Go, TypeScript, Python, Dart
**Frontend:** React, Vite, Tailwind CSS
**Backend & data:** PostgreSQL, SQL, FastAPI, REST APIs
**Other:** Docker, Docker Compose, Git, Vitest, Go's standard `testing`

I use Claude daily as part of how I work — mostly for reading unfamiliar code,
reviewing my own before I commit it, and rubber-ducking a design decision until
I can explain why I chose it. The reasoning in my READMEs is mine; the process
of getting there is usually a conversation.

---

### What I haven't done yet

I haven't deployed to AWS or run anything on Kubernetes, and I haven't set up a
CI pipeline on a project of my own — my testing has been local so far. Those are
the next things I want to learn, ideally somewhere with engineers who'll tell me
when I'm wrong.

---

📫 **jdimitola7@gmail.com**
