# PowerTeam System Report — MagicAbilities

## 🗄️ Data (SQLite)

| Table | Contents |
|---|---|
| `powerteams` | Team name, owner, color |
| `powerteam_members` | Members of each team |
| `powerteam_coowners` | Co-owners of each team |
| `powerteam_requests` | Join requests (sent by non-owners) |
| `powerteam_invites` | Invites sent by owner/co-owner to other players |

## 👤 Player commands — `/powerteam`

| Command | Function | Permission |
|---|---|---|
| `create <name> <color>` | Create a new team and auto-add yourself | Anyone |
| `add <player>` | Add a player to your own team | Owner/co-owner/admin → adds directly; regular member → sends a **request** for approval |
| `add <team> <player>` | Add directly to a specified team | Owner/co-owner/admin |
| `remove <player>` / `remove <team> <player>` | Kick a member | Owner/admin |
| `invite <player>` / `invite <team> <player>` | Send a team invite | Owner/co-owner/admin |
| `accept <team>` | Accept an invite | Invited player |
| `decline <team>` | Decline an invite | Invited player |
| `requests` | View pending join requests (opens a click-to-approve **GUI**) | Owner/co-owner/admin |
| `invites` | View invites you've received | Anyone |
| `approve <player>` | Approve a join request | Owner/co-owner/admin |
| `deny <player>` | Deny a join request | Owner/co-owner/admin |
| `list [team]` | List all teams, or a team's members | Anyone |
| `info <team>` | Show detailed info for a team | Anyone |

## 👑 Team management commands — `/powerteamowner`

| Command | Function | Permission |
|---|---|---|
| `transfer <team> <newOwner>` | Transfer team ownership | Owner/admin |
| `disband <team>` | Disband a team | Owner/admin |
| `leave` | Leave your current team (owner must transfer ownership or disband first) | Member |
| `coowner add\|remove <player>` | Add/remove a co-owner | Owner only |

## 🖱️ GUI

`/powerteam requests` opens a player-head (`PLAYER_HEAD`) inventory GUI, one item per request:
- **Left-click** = approve
- **Right-click** = deny
- The GUI automatically refreshes after each action

## 🔔 Automatic events

On player join (`PlayerJoinEvent`): if the player owns a team with pending requests, they're automatically notified.

---
