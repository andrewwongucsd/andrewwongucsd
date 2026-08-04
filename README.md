<h1 align="center">Andrew Wong</h1>

<p align="center">
  <b>Backend &amp; infrastructure engineer</b> — agent systems, Go services, and the SRE layer underneath them.
</p>

<p align="center">
  <a href="https://linkedin.com/in/andrewwongucsd">
    <img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white" alt="LinkedIn" />
  </a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Go-00ADD8?style=flat-square&logo=go&logoColor=white" alt="Go" />
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python" />
  <img src="https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white" alt="Kubernetes" />
  <img src="https://img.shields.io/badge/Terraform-7B42BC?style=flat-square&logo=terraform&logoColor=white" alt="Terraform" />
  <img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white" alt="Docker" />
  <img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white" alt="PostgreSQL" />
  <img src="https://img.shields.io/badge/LangGraph-1C3C3C?style=flat-square&logo=langchain&logoColor=white" alt="LangGraph" />
</p>

---

### What I'm building

<table>
<tr>
<td width="50%" valign="top">

#### 🔍 [sre-triage-agent](https://github.com/andrewwongucsd/sre-triage-agent)

An LLM **incident-triage agent** on LangGraph. Reads an incident, calls tools
(logs / metrics / dependency map), returns a structured diagnosis: root cause +
which team to escalate to.

The agent is the easy half. It ships with a **hand-labeled incident benchmark**,
a **validated judge** (measured against human labels via Cohen's κ), and a
**CI gate that fails the build when quality regresses**.

`Python` · `LangGraph` · `Claude` · `pytest`

</td>
<td width="50%" valign="top">

#### ☁️ [playground](https://github.com/andrewwongucsd/playground)

**A written case study, not a codebase.** How two small products — a real-time
multiplayer card game and a dev-utilities toolbox — went from a bare cloud
account to live on managed Kubernetes, and how they're *operated*.

Terraform for the network, cluster, and every machine identity. A pipeline that
scans before the registry push, signs the game's images with keyless cosign, and
refuses to call a deploy done until pods report Ready. Postgres streaming its WAL
to object storage. Burn-rate alerts, and an external probe that sits outside the
cluster's own failure domain.

It names what *isn't* done as carefully as what is.

`Kubernetes` · `Terraform` · `Go` · `Postgres` · `Observability`

</td>
</tr>
<tr>
<td width="50%" valign="top">

#### 📦 [minirun](https://github.com/andrewwongucsd/minirun)

A container runtime built from scratch to learn what Docker sits on top of:
namespaces via `clone(2)`, cgroups v2 limits, `pivot_root` filesystem isolation.

Working end to end — `minirun run` gives you a shell that thinks it's PID 1,
sees only its own rootfs, and is capped at the memory and CPU you asked for.

`Go` · `Linux internals`

</td>
<td width="50%" valign="top">

#### 🗓️ [mini-scheduler](https://github.com/andrewwongucsd/mini-scheduler)

A distributed task scheduler built from scratch to learn the control-plane logic
Kubernetes abstracts: heartbeat liveness, Filter → Score → Bind placement,
priority preemption, and rescheduling when a worker dies.

Complete and tested — kill a worker mid-task and its work lands somewhere else.
**[Watch it happen live](https://mini-scheduler.leetcodewarrior.com/)**: the
cluster kills one of its own workers every 45 seconds, on a free-tier ARM node.

`Go` · `Distributed systems`

</td>
</tr>
</table>

---

### How I work

- **Measure the thing, don't just demo it.** Anyone can call an LLM API. Knowing whether the output is *good* takes a benchmark, a judge, and a number that fails CI — so that's what I build alongside the agent.
- **Build one to make the buy decision.** `minirun` and `mini-scheduler` exist so that a build-vs-buy call on sandboxed execution comes from understanding the primitives, not from vibes. Both READMEs say plainly why the from-scratch version is *not* what should ship.
- **Write down why.** Every project says in writing what was chosen, what was rejected, and what it cost — as a decisions section, a non-goals list, or a plain statement of what still isn't done. Being honest about a prototype's limits is more useful than pretending it has none.

---

### Toolbox

**Languages** Go · Python · TypeScript · SQL · Bash
**Infra** Kubernetes · Terraform · Docker · GitHub Actions · Helm · Kustomize
**Data** PostgreSQL
**AI** LangGraph · Claude API · LLM-as-judge evaluation
