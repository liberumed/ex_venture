# GMCP Events

## Channels.Broadcast

A channel you are in had a message broadcast to it.

```
Channels.Broadcast {
  "channel": "global",
  "from": {"id": 1, "name": "Player"},
  "message": "Hi"
}
```

## Channels.Tell

A new tell message was sent to your character.

```
Channel.Tell {"from": {"id": 1, "name": "Player"}, "message": "Hi"}
```

## Character

On sign in the general character information will be sent.

```
Character {"name": "Player"}
```

## Character.Skill

Fired when a skill's active state changes.
```
Character.Skill {"name": "Magic Missile", "command": "magic missile", "active": true}
```

## Character.Vitals

Any time a player's vitals change (stats) this will be broadcast. Every tick will also push this out.

```
Character.Vitals {
  "strength": 15,
  "skill_points": 20,
  "move_points": 10,
  "max_skill_points": 20,
  "max_move_points": 10,
  "max_health_points": 30,
  "intelligence": 15,
  "health_points": 30,
  "dexterity": 15
}
```

## Config.Update

This will contain the full config that the player has, anytime it is updated.

```
Config.Update {
  "color_npc": "blue"
}
```

## Mail.New

You have received a new peice of mail.

```
Mail.New {
  "id": 1,
  "from": {"id": 1, "name": "Player"},
  "title": "Hi"
}
```

## Room.Info

When a player uses `look` or moves this will be sent to show the current room's information.

```
Room.Info {
  "id": 5,
  "zone": {"id": 1, "name": "Zone"},
  "y": 3,
  "x": 2,
  "map_layer": 4,
  "shops": [{"name": "Shoppe", "id": 1},
  "players": [{"name": "player", "id": 1}],
  "npcs": [{"name": "Bandit", "id": 2}],
  "name": "Great Room",
  "items": [{"name": "Leather Armor", "id": 2}],
  "ecology": "default",
  "exits": [{"room_id": 10, "direction": "east"}],
  "description": "The great room of the bandit hideout."
}
```

## Room.Characters.Enter

Sent when a character enters the player's room.

```
Room.Characters.Enter {"type": "player", "name": "Player", "id": 3}
```

## Room.Characters.Leave

Sent when a character leaves the player's room.

```
Room.Characters.Leave {"type": "player", "name": "Player", "id": 3}
```

## Room.Heard

Sent whenever someone `say`s to the room the player is in.

```
Room.Heard {
  "from": {"type": "player", "name": "Player", "id": 3},
  "message": "hi"
}
```

## Room.Whisper

Sent when the player is whispered to.

```
Room.Whisper {
  "from": {"type": "player", "name": "Player", "id": 3},
  "message": "hi"
}
```

## Target.Character

```
Target.Character {"type": "player", "name": "Player", "id": 3}
```

## Target.Clear

```
Target.Clear {}
```

## Target.You

Another Charcater (PC or NPC) has targeted your character.

```
Target.You {"type": "player", "name": "Player", "id": 3}
```

## Zone.Map

```
Zone.Map {"map": "..."}
```
