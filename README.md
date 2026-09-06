<div align="center">

# Discord Badges

**A complete reference for current, legacy, and experimental Discord profile badges.**

[![Discord](https://img.shields.io/badge/Discord-5865F2?style=for-the-badge\&logo=discord\&logoColor=white)](https://discord.com/)
[![Documentation](https://img.shields.io/badge/Documentation-Official-blue?style=for-the-badge)](https://discord.com/developers/docs)

<br>

A community-driven project dedicated to documenting **Discord badges**, their history, availability, recent changes, and how profile information is represented across the Discord platform.

</div>

---

<div align="center">

## About

</div>

Discord profile badges are small icons displayed on user profiles. They can represent subscriptions, server boosting, official programs, achievements, account history, and other activities across the platform.

This project aims to provide a **public reference for the Discord badge system**, documenting current, legacy, discontinued, and experimental badges.

<div align="center">

### Categories

`Current` · `Legacy` · `Experimental`

</div>

---

<div align="center">

# Current Badges

</div>

## Discord Nitro

The **Discord Nitro** badge is associated with users who have an eligible Nitro subscription.

Discord Nitro provides additional features across the platform, and the way subscription information is displayed may change as Discord updates its profile system.

---

## Server Booster

The **Server Booster** badge identifies users who support servers through Discord's Server Boosting system.

The badge has different visual levels associated with the duration of continuous boosting.

---

## Bug Hunter

The **Bug Hunter Badge** is associated with Discord's official bug-hunting program.

It is awarded to participants of the program and cannot simply be obtained through normal Discord usage.

---

## HypeSquad

**HypeSquad** badges are associated with Discord's HypeSquad program.

Historical HypeSquad badges include:

* HypeSquad Bravery
* HypeSquad Brilliance
* HypeSquad Balance
* HypeSquad Events

---

## Discord Staff

The **Discord Staff** badge identifies official members of the Discord team.

It is one of the most restricted badges on the platform.

---

## Partner

The **Partner** badge is associated with Discord's official Partner Program.

Historically, it was associated with owners of communities selected for the program.

---

<div align="center">

# New Badges & Features

</div>

Discord continues to evolve its profile system and introduce new ways of representing user information.

Recent features and experiments include:

* Discord Quests
* Orbs
* Legacy Username
* Gifting
* Account Age
* Streaming
* Game Time
* Game Variety

Some of these features may be experimental and only available to a limited number of users.

---

## Discord Quests

**Discord Quests** allow users to participate in activities and campaigns within Discord.

These experiences may be connected to:

* Games
* Applications
* Events
* Promotional campaigns

The Quest system continues to evolve as Discord introduces new experiences.

---

## Orbs

**Orbs** are part of Discord's rewards system.

The system allows users to earn and use Orbs within certain experiences and items provided by Discord.

---

## Legacy Username

The **Legacy Username Badge** is associated with Discord's previous username system.

Before the username change, Discord accounts used the format:

```text
username#0000
```

The platform later transitioned to unique usernames:

```text
@username
```

The Legacy Username Badge allows certain accounts to retain information related to the previous username system.

---

<div align="center">

# Experimental Features

</div>

Discord also tests new profile features that may only appear for selected users.

Documented experiments include:

| Feature      | Description                           |
| ------------ | ------------------------------------- |
| Gifting      | Information related to gifting        |
| Account Age  | Information related to account age    |
| Streaming    | Information related to streaming      |
| Game Time    | Information related to gaming time    |
| Game Variety | Information related to gaming variety |

These features may be changed, expanded, or removed while Discord continues testing them.

---

<div align="center">

# Legacy Badges

</div>

Some badges are no longer normally awarded but remain visible on older accounts.

Examples include:

* Early Supporter
* Partnered Server Owner
* HypeSquad Events
* HypeSquad Bravery
* HypeSquad Brilliance
* HypeSquad Balance
* Early Verified Bot Developer
* Moderator Programs Alumni
* Active Developer

These badges are important for preserving the historical identity of older Discord accounts.

---

<div align="center">

# Active Developer Badge

</div>

The **Active Developer Badge** was introduced by Discord to recognize active developers on the platform.

Discord later discontinued the badge.

Because of this, it should now be considered a **legacy badge** rather than a badge that can be obtained by new users.

---

<div align="center">

# Discord API

</div>

The Discord API provides applications with access to different types of information and functionality across the platform.

One of the most important objects for profile information is the **User Object**.

A simplified example:

```json
{
  "id": "123456789012345678",
  "username": "example",
  "global_name": "Example",
  "avatar": "avatar_hash",
  "public_flags": 64
}
```

Important fields include:

| Field          | Description            |
| -------------- | ---------------------- |
| `id`           | Unique Discord user ID |
| `username`     | Current username       |
| `global_name`  | Global display name    |
| `avatar`       | User avatar hash       |
| `public_flags` | Public account flags   |

---

<div align="center">

# Public Flags

</div>

The `public_flags` field represents a collection of **public bit flags** associated with a Discord account.

Conceptually:

```text
public_flags
      ↓
   Bitfield
      ↓
 Public Flags
      ↓
 Badge / Status
```

Certain historical and public badges can be identified through these flags.

However, **not every piece of profile information is represented by a `public_flag`**.

---

<div align="center">

# Not Every Badge Is a Public Flag

</div>

This is one of the most important distinctions when working with Discord profile data.

It should not be assumed that:

```text
1 badge = 1 public_flag
```

Discord's modern profile system can obtain or display information from multiple sources.

These may include:

```text
User Object
     +
Profile Data
     +
Activities
     +
Subscriptions
     +
Server Boosting
     +
Privacy Settings
     +
Experimental Features
```

Therefore, `public_flags` represents only **one part of the modern Discord profile system**.

---

<div align="center">

# Modern Profile System

</div>

Discord's modern profile system contains significantly more information than the original badge system.

Profiles can contain or reference:

* Badges
* Activities
* Connected accounts
* Biography
* Custom status
* Server information
* Account information
* Experimental profile features

The information available to an application can depend on Discord's API rules, permissions, and the user's privacy settings.

---

<div align="center">

# Profile Privacy

</div>

Discord has introduced additional **Profile Privacy** controls that allow users to determine how certain profile information is displayed.

Depending on the user's settings, information such as the following may be hidden:

* Badges
* Activities
* Connected accounts
* Biography
* Custom status
* Widgets
* Wishlists

Other information may remain visible, including:

* Avatar
* Banner
* Username
* Display name
* Server Tag
* Certain account information

This means applications should never assume that every profile will expose the same information.

---

<div align="center">

# Usernames

</div>

Discord went through a major change to its username system.

### Previous System

```text
username#1234
```

### Current System

```text
@username
```

Modern Discord usernames are unique and no longer use the previous four-digit discriminator.

This transition is also directly related to the **Legacy Username Badge**.

---

<div align="center">

# The New Discord API

</div>

The modern Discord ecosystem extends far beyond the traditional REST API.

Discord currently provides several systems and technologies for developers:

```text
Discord Platform
│
├── REST API
├── Gateway
├── OAuth2
├── Interactions
├── Webhooks
├── Rich Presence
└── Social SDK
```

Each system has its own purpose, permissions, limitations, and available data.

---

<div align="center">

# Why This Project?

</div>

This project exists to document the evolution of Discord's badge and profile systems.

The goal is to make it easy to understand:

**Which badges currently exist?**

**Which badges can still be obtained?**

**Which badges are legacy?**

**Which badges have been discontinued?**

**Which features are experimental?**

**How does the Discord API represent this information?**

**Which profile information can be hidden through privacy settings?**

---

<div align="center">

# Disclaimer

</div>

This project is **independent** and is not affiliated with, sponsored by, or endorsed by Discord.

Discord and its respective trademarks, logos, icons, and visual assets belong to their respective owners.

The information contained in this project is intended for **documentation, research, and development purposes** related to the Discord platform.

<br>

### Official Sources

[Discord Developer Documentation](https://discord.com/developers/docs)

[Discord Support](https://support.discord.com/)

[Discord Developer Changelog](https://discord.com/developers/docs/change-log)

[Discord Social SDK](https://discord.com/developers/docs/social-sdk/)

<br>

**Made for documentation and research.**

</div>
