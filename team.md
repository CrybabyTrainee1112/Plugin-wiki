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
| `create <name> [color]` | Create a new team and auto-add yourself. `color` is optional — if omitted, a random color is picked. Invalid color names are rejected with a suggested list. | Anyone |
| `add <player>` | Add a player to your own team | Owner/co-owner/admin → adds directly; regular member → sends a **request** for approval |
| `add <team> <player>` | Add directly to a specified team | Owner/co-owner/admin |
| `remove <player>` / `remove <team> <player>` | Kick a member | Owner/admin |
| `invite <player>` / `invite <team> <player>` | Send a team invite | Owner/co-owner/admin |
| `accept <team>` | Accept an invite | Invited player |
| `decline <team>` | Decline an invite | Invited player |
| `requests` | Open the join-requests **GUI** (see below) | Owner/co-owner/admin |
| `invites` | View invites you've received | Anyone |
| `approve <player>` | Approve a join request (text fallback if GUI unavailable) | Owner/co-owner/admin |
| `deny <player>` | Deny a join request (text fallback if GUI unavailable) | Owner/co-owner/admin |
| `list` | Open the all-teams overview **GUI** (see below) | Anyone |
| `list <team>` | Show detailed info for one team (text) | Anyone |

## 👑 Team management commands — `/powerteamowner`

| Command | Function | Permission |
|---|---|---|
| `transfer <team> <newOwner>` | Transfer team ownership | Owner/admin |
| `disband <team>` | Disband a team (also clears the team's scoreboard color for all members) | Owner/admin |
| `leave` | Leave your current team (owner must transfer ownership or disband first) | Member |
| `coowner add\|remove <player>` | Add/remove a co-owner | Owner only |
| `color <team> <color>` | Change a team's color after creation; re-applies to every online member immediately | Owner/co-owner/admin |

## 🎨 Team color → nametag sync

Team color is no longer just a stored value — it's actively applied to every member's **nametag above the head and tab-list name** via a Bukkit Scoreboard Team per PowerTeam (`TeamColorSync`).

- Suggested colors (also used for random pick on `create`): `RED, DARK_RED, GOLD, YELLOW, GREEN, DARK_GREEN, AQUA, DARK_AQUA, BLUE, DARK_BLUE, LIGHT_PURPLE, DARK_PURPLE`.
- Synced automatically on: player join, team create, being added/approved into a team, invite accept, being removed/leaving (color cleared), team disband (color cleared for all former members), and `/powerteamowner color`.

## 🖱️ GUIs

### `/powerteam requests`
54-slot inventory, paginated, up to **4 requests per page**:
- Each request is a 3-slot cluster: **player head** (target, with requester + timestamp in the lore) → **red wool "Deny"** → **lime wool "Accept"**.
- Two clusters per row, with spacer rows between rows of clusters for readability.
- Bottom-right corner: red wool `<- Previous Page` / white wool `Next Page ->`, shown only when applicable.
- If there are no pending requests, the GUI still opens and shows a barrier item saying "No pending requests" instead of staying closed.
- Only the owner, co-owner, or an admin can click Accept/Deny.

### `/powerteam list`
54-slot inventory, paginated, up to **5 teams per page**, one column per team (columns 0/2/4/6/8):
- Row 1 of each column: a black-glass **team name plaque** (colored per the team's color), lore shows owner + member count.
- Rows 2–4: up to 3 member **player heads** (owner tagged `(Owner)`); if a team has more members, the last slot becomes a "+N more" paper.
- Bottom-right corner: red wool `<- Previous Page` / lime wool `Next Page ->`, shown only when applicable.

## 🔔 Automatic events

On player join (`PlayerJoinEvent`):
- Team color is re-synced to the player's nametag/tab-list.
- If the player owns a team with pending requests, they're automatically notified in chat.

---
