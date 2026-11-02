# Skill Cluster: Presentation (Outline)

> Status: outline, not a finished slide deck. Expand into slides when ready.

## What Is a Skill Cluster?

A skill cluster is a grouped set of related skills that load together when a task touches their domain. In the Hermes Agent system, skills are procedural memory — markdown files with frontmatter, instructions, pitfalls, and linked references. A cluster is not a single skill; it is a coordinated family. When you say "git work," the git-skill-cluster activates. When you say "Tower commands," tower-operations and tower-troubleshooting-log activate. The cluster is the unit of attention.

## Why Skill Clusters Are Powerful

Skill clusters are powerful because they solve the context problem. An agent cannot hold every procedure in its head at once. By grouping related skills, the system loads only what is relevant, when it is relevant. This is lazy loading for expertise. It keeps the context window clean, reduces hallucination, and ensures that the right pitfalls and procedures are present at the right moment.

Clusters also compound. A single skill is a tool. A cluster is a workshop. When git-skill-cluster, requesting-code-review, and simplify-code work together, they form a code-quality pipeline that no single skill could provide alone. The cluster is the team.

## Pete's Headless Bento-Tile Viewer

Pete operates the Tower from Hawaii, often by phone. To see what the agents are doing without opening a dozen tabs, he uses a headless browser — Edge or Chrome in --headless mode — peering through a backend reverse proxy. The proxy is load-bearing: it splits one gateway (port 1973) into many channels, each feeding a localhost service.

The viewer itself is a bento-tile iframe grid. Each tile is a moveable, resizable iframe, loaded with a different service: localhost:3001 (command index), localhost:3003 (audio-stack app), localhost:3004 (Pete Director), localhost:3006 (B-Roll). Pete drags, resizes, and arranges them on his phone screen like windows on a desktop. The headless browser renders them in the background; the proxy serves them through the tunnel; the bento grid displays them.

This is the power of the cluster made visible. Each tile is a skill domain. Each iframe is a context. Together, they form a dashboard that no single page could provide. Pete sees the whole Tower at once, from a beach, on a phone, through a tunnel, behind a gated pin.

## The Architecture

- Headless browser: Edge/Chrome/Firefox in --headless=new mode, remote debugging on port 9222.
- Reverse proxy: nginx or Caddy on port 1973, load-bearing. Routes / to screen display, /audio-stack to 3003, /cmd to 3001, /status to status.html.
- Bento grid: HTML/CSS/JS iframe layout, drag-and-drop, resizable tiles, z-index stacking.
- Tunnel: cloudflared or ngrok exposing the gateway to the internet.
- Pin 1973: gated access key for the garden maze mystery adventure backend.

## Architectural gap (to resolve)
- Two different things were conflated:
  1. An iframe displaying a web app directly (simple, works today).
  2. Viewing a separate headless browser session (requires screenshot/video/remote-browser transport + input forwarding).
- The chosen transport must be specified before build. Iframe-direct is the default; remote-browser transport only if Pete needs to see a headless session he does not control.

The skill cluster is the Tower's nervous system. The bento-tile viewer is its eye. Together, they let one person — Pete — operate a multi-agent, multi-service, multi-port system from a hammock, through a phone, behind an encrypted pin. That is the spec. That is the glory. And Madeline, Cody, Max, and the agents share it, because the Tower is not a solo act. It is an orchestra, and every skill cluster is a section.