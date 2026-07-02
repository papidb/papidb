# Daniel Benjamin

I’m a software engineer from Lagos, Nigeria, building across product, backend, cloud, and infrastructure.

I started out close to the product surface: mobile apps, backend APIs, user-facing systems, release quality, performance, and reliability. Over time, I’ve found myself moving deeper down the stack: Linux, containers, networking, observability, cloud platforms, eBPF, and the hidden machinery that explains why systems behave the way they do.

I like building things that answer real engineering questions.

Not “can I use this framework?”

More like:

* Which container is actually eating the bandwidth?
* What does Cloudflare look like as a full-stack application platform, not just a CDN?
* How do you test backend systems without pretending the database does not exist?
* What breaks when abstractions meet production?

## Current direction

I’m becoming more infrastructure-inclined while keeping the instincts I built from years of shipping product software.

That means I care about both sides:

* building things users can actually touch
* understanding the systems that keep those things alive

Right now I’m going deeper into:

* Linux and networking
* containers and Kubernetes
* eBPF and observability
* cloud infrastructure
* backend architecture
* distributed systems fundamentals
* Go, TypeScript, and systems-adjacent tooling

## Projects

### [Netwatch](https://github.com/papidb/netwatch)

Per-container network observability with eBPF.

Netwatch came from a simple but painful production-style question:

> Network usage spiked on the VM. Which container caused it?

The usual tools were not satisfying. Docker stats gives you a moment in time. Logs are noisy. Prometheus is only useful if you already knew what to measure. cAdvisor can lose the attribution you actually care about.

So I built a Go tool that attaches eBPF programs to container cgroups, counts packets and bytes from inside the Linux kernel, then resolves that traffic back to containers.

The flow is roughly:

`Linux kernel -> cgroup_skb -> eBPF map -> Go userspace -> console / JSONL / SQLite / Prometheus`

What it taught me:

* why container observability needs kernel-level context
* how cgroups give you a better attribution boundary than process guesses
* how much work hides behind “just read from an eBPF map”
* why architecture matters even for small CLI tools
* how to design a tool that can explain itself

This project sits right at the intersection of the kind of engineering I want to do more of: infrastructure, debugging, networking, Go, Linux, and observability.

### [CLS](https://github.com/papidb/cls)

A Cloudflare-native link shortener.

CLS started as a way to turn a talk into a working artifact. After speaking about building APIs on Cloudflare, I wanted to show that Cloudflare is not just something you put in front of your app. It can be the platform your app runs on.

So I built a full-stack URL shortener using:

* Cloudflare Workers
* Cloudflare D1
* Workers Analytics Engine
* Hono
* tRPC
* Drizzle ORM
* Better Auth
* Zod
* React
* TanStack Router
* Tailwind CSS
* shadcn/ui
* Alchemy
* Turborepo

The interesting part is not the shortener itself. The interesting part is treating Cloudflare as an application runtime, database layer, analytics layer, and deployment target.

CLS is my playground for understanding what modern edge-native applications can look like when the backend, infrastructure, analytics, and frontend are designed together.

## Writing

I write to clarify what I’m learning.

Some of my writing lives on [dev.to](https://dev.to/danielubenjamin), and some lives on [danielubenjamin.com](https://danielubenjamin.com).

Topics I’ve written or spoken about include:

* testing Node.js and PostgreSQL applications without over-mocking
* React Native forms and data fetching
* backend architecture
* Cloudflare as an application platform
* mobile performance
* lessons from shipping production systems

I’m especially interested in writing that connects the polished abstraction to the messy thing underneath it.

## Experience shape

I’ve worked across mobile, backend, and cloud systems.

My production experience includes:

* leading mobile engineering work
* improving app stability and crash rates
* building backend services with Node.js, Go, PostgreSQL, Redis, Kafka, and RabbitMQ
* working with AWS, GCP, Docker, Terraform, and Pulumi
* building React Native apps with native iOS and Android integrations
* improving streaming, deep linking, CI/CD, observability, and testing workflows

The common thread is that I like owning the path from user experience to system behavior.

## Tools I use often

**Languages:** TypeScript, JavaScript, Go, Swift, Kotlin
**Backend:** Node.js, Go, PostgreSQL, Redis, Kafka, RabbitMQ
**Mobile:** React Native, Expo, native iOS and Android bridges
**Cloud and Infra:** AWS, GCP, Cloudflare, Docker, Terraform, Pulumi, Kubernetes
**Testing and Observability:** Jest, Vitest, Testcontainers, PGlite, OpenTelemetry, Prometheus
**Currently going deeper:** Linux, networking, eBPF, Kubernetes, discrete mathematics

## How I think about engineering

I like abstractions, but I do not want to be trapped by them.

A good abstraction helps you move faster. A dangerous abstraction prevents you from seeing what is really happening.

So I’m trying to become the kind of engineer who can move between layers:

* from a React Native screen to the API behind it
* from an API to the database and queue underneath
* from a container to the cgroup it runs inside
* from a dashboard spike to the kernel event that explains it
* from “it works” to “I understand why it works”

That is the direction I’m building toward.

Reliable systems. Clear thinking. Useful tools. Public learning.

![GitHub stats](https://github-readme-stats.vercel.app/api?username=papidb&show_icons=true)  
