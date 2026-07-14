<p align="center">
  <a href="https://picorca.com/">
    <img src="https://github.com/user-attachments/assets/7bcf4baa-e2eb-4854-87c4-680b5eb02137" alt="Picorca" width="400" />
  </a>
</p>

<p align="center">
  <strong>A private, peer-to-peer workspace for image assets and creative collaboration.</strong>
</p>

<p align="center">
  <a href="https://picorca.com/">Website</a> ·
  <a href="https://github.com/POrcaTeam/Picorca/releases">Download</a> ·
  <a href="https://github.com/POrcaTeam/Picorca/discussions">Community</a> ·
  <a href="https://picorca.com/feedback-form">Feedback</a>
</p>

---

## Overview

Picorca is a desktop application for organizing, sharing, and collaborating on image assets without making a centralized cloud service the source of truth. Your project stays on your device; when you choose to collaborate, Picorca uses peer-to-peer networking to connect authorized participants and synchronize the work that belongs to the shared project.

It is built for designers, creative teams, and AI-assisted workflows that need an image library that is both easy to browse and under the team's control. Create a project, import assets, organize them with folders and tags, then share the project with the people who need access.

Picorca is developed by POrca Team. We are grateful to the [Iroh](https://github.com/n0-computer/iroh) team, whose networking technology helps make our peer-to-peer vision possible.

## Why Picorca

|                                | What it means                                                                                                   |
| ------------------------------ | --------------------------------------------------------------------------------------------------------------- |
| **Local-first ownership**      | Projects and assets live locally, giving you control over where your work is stored.                            |
| **Peer-to-peer collaboration** | Share projects directly with authorized collaborators instead of moving your library into a central repository. |
| **Built for visual work**      | Browse, search, tag, preview, edit, and export image assets from one desktop workspace.                         |
| **Ready for AI workflows**     | Let AI clients work with the current project through a local MCP server.                                        |

## Features

### Organize a growing asset library

- Import image assets and preserve a clear folder structure.
- Use folders, tags, metadata, previews, and search to find the right asset quickly.
- Inspect image information and AI-related metadata in the app.
- Export selected assets back to disk when you need them elsewhere.

### Collaborate without giving up control

- Create personal or shared projects based on your workflow.
- Invite collaborators with a share ticket and synchronize project content in real time.
- Support direct peer connections, with relay assistance available for complex networks.
- Keep access credentials private: anyone with a share ticket may be able to join the associated project.

### Work across your creative toolchain

- Edit and manage assets in a dedicated desktop environment.
- Use built-in multilingual translation for text and image-based content.
- Use semantic image search to explore visually similar assets.
- Configure asset output and compression preferences to better manage local storage.

## MCP for AI-assisted asset workflows

Picorca includes a [Model Context Protocol (MCP)](https://modelcontextprotocol.io/) server so local AI clients—such as Codex—can work with the project currently open in Picorca. This makes generated assets part of the same organized library as the rest of your work, rather than leaving them scattered across downloads and temporary folders.

With MCP enabled, an AI client can:

- Inspect the current project, folders, tags, supported asset types, and asset metadata.
- Search image assets, including vector-based similarity search where available.
- Import one or multiple generated assets into the current project.
- Create folders, add tags, and move assets to keep the library organized.
- Read asset previews and metadata for use in downstream creative workflows.

### Connect an MCP client

1. Open a project in Picorca.
2. Go to **Settings → MCP Service** and turn on **Enable MCP**.
3. Copy the generated **MCP Config** into your MCP client's configuration.
4. Keep Picorca running while the client uses the project.

Picorca serves MCP only on your local machine at `127.0.0.1` and requires the generated Bearer token. Treat that token like a password and refresh it from Settings if it is ever exposed. You can also enable **Read-only Mode** to let a client inspect assets without allowing imports, tagging, or moves.

The configuration shown in Picorca follows this shape; use the exact URL and token that the app provides:

```json
{
  "mcpServers": {
    "picorca": {
      "url": "http://127.0.0.1:<port>/mcp",
      "headers": {
        "Authorization": "Bearer <your-token>"
      }
    }
  }
}
```

## Getting started

1. Download and install the latest version from [GitHub Releases](https://github.com/POrcaTeam/Picorca/releases).
2. Launch Picorca and create a project, or open an existing one.
3. Drag files or folders into the project to import them.
4. Organize assets with folders and tags, then share a project when you are ready to collaborate.

For product updates and guides, visit [picorca.com](https://picorca.com/).

## Platform availability

| Platform                        | Status                                                                       |
| ------------------------------- | ---------------------------------------------------------------------------- |
| **macOS 13 (Ventura) or later** | Available now — Intel (x86_64) and Apple Silicon (ARM64) Macs are supported. |
| **Windows**                     | Planned for a future release.                                                |
| **Linux**                       | Not currently supported.                                                     |

We will share Windows availability through [GitHub Releases](https://github.com/POrcaTeam/Picorca/releases) and the [Picorca website](https://picorca.com/). No release date has been announced yet.


## Community and feedback

- Need help or want to share an idea? Start a conversation in [GitHub Discussions](https://github.com/POrcaTeam/Picorca/discussions/new?category=help).
- Found a problem? Please open a clear issue with steps to reproduce it.
- Have product feedback? Send it through the [feedback form](https://picorca.com/feedback-form).
- Help improve translations on [Crowdin](https://crowdin.com/project/picorca).

## Roadmap

We are continuing to improve peer-to-peer collaboration, asset organization, AI-assisted workflows, and language support. Windows support is planned; timing and scope will be announced when ready.

## Security note

Picorca provides local-first and peer-to-peer capabilities, but the safety of shared work also depends on how you manage access. Share tickets and MCP tokens grant access to project resources—send them only through channels you trust, and rotate MCP tokens if needed.
