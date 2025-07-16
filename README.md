# Roblox Queuing System (1v1) – Expandable Framework

This is a basic yet expandable 1v1 queuing and matchmaking system built for Roblox.  
It includes a memory-based queue, matchmaking handler, and simple mode manager.

---

## 🔧 Features

- 📦 Queue management (enqueue/dequeue players)
- 🤼 1v1 matchmaking (with easy extension for 2v2, FFA, etc.)
- 🧠 Profile reference system (for storing per-player profiles in memory)

---

## 📁 Modules Overview

### 1. `Queue.lua`
- Handles EnQueue, DeQueue, and size checking.

### 2. `MatchMaking.lua`
- Requests matches based on mode (`1v1`)
- Groups 2 players from the queue and initializes the match.

### 3. `Modes.lua`
- Holds supported game modes (`1v1` currently).

### 4. `ProfileManager.lua`
- Stores and retrieves session-based player profiles.

---

## 🧪 Example Usage

```lua
local Queue = require(path.To.Queue).new()
Queue:EnQueue(player)

local MatchMaking = require(path.To.MatchMaking)
local match = MatchMaking.request("1v1", Queue)
if match then
    match:Init()
end
