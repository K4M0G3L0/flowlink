# FlowLink

**Intelligent logistics and fleet coordination platform for transport operations in emerging markets.**

FlowLink replaces fragmented WhatsApp groups and phone-based dispatching with a structured, real-time coordination system — connecting businesses, dispatchers, and drivers in a single platform designed to scale from a 5-vehicle fleet to industrial operations.

---

## The Problem

Logistics operations across mining, construction, and transport sectors in South Africa run on manual coordination — phone calls, WhatsApp groups, and spreadsheets. The result:

- Jobs get lost, duplicated, or assigned to the wrong driver
- Dispatchers have no live view of fleet activity
- Managers have no data to make better decisions
- Trust breaks down between operators and clients

FlowLink solves this with a centralized, role-based system that brings structure, visibility, and intelligence to every movement in your fleet.

---

## What FlowLink Does

| Feature | Description |
|---|---|
| Job assignment | Dispatchers create and assign jobs to drivers in real time |
| Live job board | Full visibility of pending, active, and completed jobs |
| Driver status updates | Drivers accept, start, and complete jobs directly in the app |
| Role-based access | Separate views and permissions for admins, dispatchers, and drivers |
| Activity reporting | Track jobs completed, driver performance, and operational trends |
| Secure comms | Protected route data, location handling, and user authentication |

---

## User Roles

FlowLink is built around three operational roles, each scoped to their function:

**Admin**
- Full system access
- Manages users, roles, and company settings
- Views all reporting and analytics

**Dispatcher**
- Creates and assigns jobs
- Monitors live job board
- Communicates updates to drivers

**Driver**
- Receives job notifications
- Updates job status (accepted → in progress → completed)
- Views own assignment history

---

## Tech Stack

| Layer | Technology |
|---|---|
| Backend | Python (Flask) |
| Database | SQLite (development) → PostgreSQL (production) |
| Authentication | JWT-based role authentication |
| API | REST API |
| Frontend | HTML / CSS / JavaScript (v1) |
| Deployment | Local → Render / Railway (planned) |

---

## Project Structure

```
flowlink/
├── app/
│   ├── __init__.py
│   ├── models/
│   │   ├── user.py
│   │   ├── job.py
│   │   └── fleet.py
│   ├── routes/
│   │   ├── auth.py
│   │   ├── jobs.py
│   │   ├── dispatcher.py
│   │   └── driver.py
│   ├── static/
│   └── templates/
├── config.py
├── requirements.txt
├── run.py
└── README.md
```

---

## Getting Started

### Prerequisites

- Python 3.10+
- pip
- Git

### Installation

```bash
# Clone the repository
git clone https://github.com/kamogelo-kgashane/flowlink.git
cd flowlink

# Create a virtual environment
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Set up environment variables
cp .env.example .env

# Run the development server
python run.py
```

### Environment Variables

```env
SECRET_KEY=your_secret_key_here
DATABASE_URL=sqlite:///flowlink.db
FLASK_ENV=development
```

---

## API Overview

### Authentication

| Method | Endpoint | Description |
|---|---|---|
| POST | `/api/auth/register` | Register a new user |
| POST | `/api/auth/login` | Login and receive JWT token |
| POST | `/api/auth/logout` | Invalidate session |

### Jobs

| Method | Endpoint | Description |
|---|---|---|
| GET | `/api/jobs` | List all jobs (role-filtered) |
| POST | `/api/jobs` | Create a new job (dispatcher/admin) |
| GET | `/api/jobs/:id` | Get job details |
| PATCH | `/api/jobs/:id/status` | Update job status |
| DELETE | `/api/jobs/:id` | Cancel a job (admin only) |

### Users

| Method | Endpoint | Description |
|---|---|---|
| GET | `/api/users` | List users (admin only) |
| POST | `/api/users` | Create user (admin only) |
| PATCH | `/api/users/:id/role` | Update user role |

---

## Roadmap

### v1.0 — Core Coordination (Current)
- [x] Project structure and architecture
- [ ] User authentication with role-based access
- [ ] Job creation and assignment system
- [ ] Live dispatcher job board
- [ ] Driver status update flow
- [ ] Basic activity reporting

### v1.1 — Intelligence Layer
- [ ] Route optimisation suggestions
- [ ] Driver-to-job matching algorithm
- [ ] Demand prediction (peak period alerts)
- [ ] Performance insights dashboard

### v2.0 — Scale & Integrations
- [ ] Mobile app for drivers (React Native)
- [ ] GPS live tracking integration
- [ ] Payment and invoicing module
- [ ] Predictive vehicle maintenance alerts
- [ ] Enterprise API for third-party integrations
- [ ] Mining sector compliance features

---

## Security

FlowLink is designed with security as a first-class concern:

- JWT token authentication with role validation on every protected route
- Role-based access control — users can only access data scoped to their role
- Sensitive data (routes, cargo details, location) handled with privacy by default
- Input validation and sanitisation on all API endpoints
- Audit logging for admin actions (v1.1)

---

## Target Markets

**Phase 1 — Small to mid-size transport operators**
Fleets of 5–50 vehicles currently coordinating over WhatsApp and phone calls.

**Phase 2 — Construction and mining logistics**
High-value, high-frequency job dispatch in industrial environments where coordination failures are costly.

**Phase 3 — Enterprise and third-party integrations**
Large-scale fleet operations requiring API integrations with ERP, payroll, and compliance systems.

---

## Contributing

FlowLink is currently in active early development. Contributions, feedback, and issue reports are welcome.

```bash
# Create a feature branch
git checkout -b feature/your-feature-name

# Commit your changes
git commit -m "feat: describe your change"

# Push and open a pull request
git push origin feature/your-feature-name
```

Commit convention: `feat:` / `fix:` / `docs:` / `refactor:` / `test:`

---

## Author

**Kamogelo Kgashane**
Software Engineer | AI Systems Builder | NQF 6 — WeThinkCode_

- Email: kgashanekamogelo@gmail.com
- LinkedIn: [linkedin.com/in/kamogelo-kgashane-9436a9231](https://www.linkedin.com/in/kamogelo-kgashane-9436a9231)
- GitHub: [github.com/kamogelo-kgashane](https://github.com/kamogelo-kgashane)

---

## License

MIT License — see [LICENSE](LICENSE) for details.

---

*FlowLink is being built to bring intelligent coordination to logistics operations in underserved and high-demand markets. Starting in South Africa. Built to scale.*
