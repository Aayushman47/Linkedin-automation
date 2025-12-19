 		POC for LinkedIn Automation - Golang + Rod


Overview

This proof-of-concept demonstrates the browser automation architecture using Go and Rod.

It focuses on human-like behavior, safety controls, and cleanliness in modular design.


Disclaimer

⦁	use strictly for educational/evaluation purpose only.

⦁	Automation of LinkedIn violates the ToS established by them.

⦁	By default, live execution is disabled.



Features

⦁	Environment-based authentication - demo-enabled

⦁	Login failure & checkpoint detection

⦁	Search & profile discovery

⦁	Pagination & duplicate handling

⦁	Connection requests (dry-run)

⦁	Messaging Templates-system (dry-run)

⦁	Scheduler-business hours

⦁	Rate Limiting: one can limit it to a certain number per day/hour.

⦁	Persistent state tracking



Safety Design

⦁	DRY_RUN="true" disables all irreversible actions

⦁	Compilation to assembly requires explicit opt-in

⦁	By default, no credentials are hardcoded.

⦁	DEMO_AUTH="true" runs the authentication in demo.


Run

⦁	DRY_RUN=true DEMO_AUTH=true go run ./app/bot  (for MacOS and LINUX)
⦁	$env:DEMO_AUTH="true"; $env:DRY_RUN="true"; go run ./app/bot  (for WindowsOS)


Architecture

⦁	Each feature is a self-contained module under internal/, and main.go acts as the orchestrator.


Project Structure


Linkedin-automation-project/
├── app/
│   └── bot/
│       └── main.go
│
├── internal/
│   ├── auth/
│   │   ├── auth.go
│   │   ├── cookies.go
│   │   └── detector.go
│   │
│   ├── browser/
│   │   └── browser.go
│   │
│   ├── config/
│   │   └── config.go
│   │
│   ├── connect/
│   │   └── connect.go
│   │
│   ├── logger/
│   │   └── logger.go
│   │
│   ├── message/
│   │   ├── message.go
│   │   └── template.go
│   │
│   ├── persistence/
│   │   └── store.go
│   │
│   ├── search/
│   │   ├── search.go
│   │   ├── parser.go
│   │   └── paginator.go
│   │
│   └── stealth/
│       ├── actions.go
│       ├── mouse.go
│       ├── scroll.go
│       ├── scheduler.go
│       ├── ratelimit.go
│       └── timing.go
│
├── go.mod
├── go.sum
├── README.md
└── state.json
