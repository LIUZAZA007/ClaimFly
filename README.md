# ClaimFly

<p align="center">
<strong>Flight plugin for WorldGuard regions with ProtectionStones integration</strong>
</p>

<p align="center">
<img src="https://img.shields.io/badge/Version-1.0-brightgreen?style=for-the-badge" alt="Version" />
<img src="https://img.shields.io/badge/API-1.21+-blue?style=for-the-badge" alt="API Version" />
<img src="https://img.shields.io/badge/Java-21+-orange?style=for-the-badge" alt="Java" />
<img src="https://img.shields.io/badge/Folia-Supported-purple?style=for-the-badge" alt="Folia" />
</p>

---

## Overview

ClaimFly is a lightweight flight plugin designed for Minecraft servers using WorldGuard and ProtectionStones. It allows players to fly within their own claims or claims where they are trusted members, providing a seamless flying experience with automatic region detection.


### Supported Plugins
ClaimFly integrates seamlessly with a wide range of popular plugins:
- **ProtectionStones** 
- **RedProtect** 

### Key Features

- **Claim-Based Flight** - Fly only within your own claims or claims where you're a trusted member
- **Auto-Fly** - Automatically enable flight when entering a claim (optional)
- **Damage Protection** - Automatically disable flight when taking damage (configurable)
- **Fall Damage Prevention** - Prevents fall damage when flight is disabled due to damage or leaving a region
- **Custom Command Aliases** - Configure custom command aliases via config.yml
- **Region Size Filtering** - Restrict flight based on region size (min/max area for RedProtect)
- **PlaceholderAPI Support** - Custom placeholders for other plugins
- **Folia Ready** - Full support for multi-threaded region servers

---

## Installation

### Quick Start

1. Download `ClaimFly.jar` from releases
2. Place in your server's `plugins` folder
3. Restart the server to generate configuration files
4. Configure `config.yml` to your needs
5. Reload with `/claimfly reload` or `/cf reload`

### Dependencies

**Required:**
- Java 21 or higher
- Paper 1.21+ (or Folia, Spigot 1.21+ compatible)

---

## Commands

| Command | Description | Permission |
|---------|-------------|------------|
| `/claimfly` | Toggle flight for yourself | `claimfly.use.command` |
| `/claimfly <player>` | Toggle flight for another player | `claimfly.admin.command` |
| `/claimfly reload` | Reload plugin configuration | `claimfly.reload.command` |

**Default Aliases:** `cf`, `fly` (configurable in `config.yml`)

---

## Permissions

| Permission | Description | Default |
|------------|-------------|---------|
| `claimfly.use.command` | Allows use of the `/claimfly` command | `false` |
| `claimfly.others` | Allows flying in claims where you are a trusted member | `false` |
| `claimfly.autofly` | Automatically enables flight upon entering a claim | `false` |
| `claimfly.admin.command` | Grants access to `/claimfly <player>` | `op` |
| `claimfly.reload.command` | Grants access to `/claimfly reload` | `op` |

---

## PlaceholderAPI

If PlaceholderAPI is installed, the following placeholders are available:

- `%claimfly_status%` - Returns "enabled" or "disabled" based on flight status

---

## How It Works

1. **Region Detection** - The plugin continuously monitors player movement and detects when they enter or leave WorldGuard regions
2. **Ownership Check** - Uses ProtectionStones API to verify if the player is the owner or a trusted member of the region
3. **Alias Filtering** - If configured, checks if the region's ProtectionStones alias is in the allowed list
4. **Flight Management** - Automatically enables/disables flight based on region entry/exit
5. **Safety Features** - Prevents fall damage when flight is disabled and automatically disables flight on damage, death, world change, or server quit

---

## Folia Support

ClaimFly fully supports Folia's multi-threaded region system. The plugin automatically detects Folia and uses the appropriate scheduler:

- **Folia**: Uses region-based and entity-based schedulers
- **Paper/Bukkit**: Uses standard Bukkit scheduler

No additional configuration needed!

---

## License & Credits

**ClaimFly** is developed and maintained with care by **Chaliu**.

---

## Support

For issues, questions, or feature requests, please open an issue on the project repository.

