---
title: Alchemy Developers

language_tabs: # must be one of https://git.io/vQNgJ
  - json

toc_footers:
  - <a href='https://github.com/alchemyrpg/slate'>❤️ Open-Source</a>

includes:
  - ogl

search: true

code_clipboard: true

meta:
  - name: description
    content: Alchemy developer documentation
---

# Introduction

Welcome to the Alchemy developer documentation! We don't have a lot available for developers today, but we hope that will change soon. :)

# Character Import

Alchemy Unlimited provides the ability to import NPCs into a universe that you are an editor of. Today, this is a file-based import process, but we may open up an API for this in the future.

The import process only supports JSON.

## Importing a single NPC

To import a single NPC, create a JSON file with a single `Character` object in it.

### Character

| Field | Type | Description |
| ----- | ---- | ----------- |
| `name` | `string` | The name of the character. |

```json
{
  {
    "abilityScores": [
        {
            "name": "str",
            "value": 10
        },
        {
            "name": "dex",
            "value": 10
        },
        {
            "name": "con",
            "value": 10
        },
        {
            "name": "int",
            "value": 10
        },
        {
            "name": "wis",
            "value": 14
        },
        {
            "name": "cha",
            "value": 11
        }
    ],
    "actions": [
        {
            "description": "Melee Weapon Attack: +2 to hit, reach 5 ft., one target. Hit: 2 (1d4) bludgeoning damage.",
            "name": "Club",
            "sortOrder": 0,
            "steps": [
                {
                    "attack": {
                        "ability": "str",
                        "crit": 20,
                        "damageRolls": [
                            {
                                "abilityName": "str",
                                "dice": "1d4",
                                "type": "Bludgeoning"
                            }
                        ],
                        "isProficient": true,
                        "isRanged": false,
                        "name": "Club",
                        "savingThrow": {
                        }
                    },
                    "journalCommand": {
                    },
                    "skillCheck": {
                    },
                    "type": "custom-attack"
                }
            ]
        }
    ],
    "alignment": "Any Alignment",
    "armorClass": 10,
    "challengeRating": "1/4",
    "classes": [
        {
            "class": "Monster",
            "level": 1
        }
    ],
    "currentHp": 9,
    "exp": 50,
    "hitDice": "2d8",
    "imageUri": "https://cdn.alchemyrpg.com/app-assets/humanoid-token.svg",
    "initiativeBonus": 0,
    "isNPC": true,
    "isSpellcaster": true,
    "maxHp": 9,
    "movementModes": [
        {
            "distance": 30,
            "mode": "Walking"
        }
    ],
    "name": "Acolyte 3",
    "proficiencies": [
        {
            "name": "Common",
            "type": "language"
        }
    ],
    "proficiencyBonus": 2,
    "race": "NPC",
    "size": "Medium",
    "skills": [
        {
            "abilityName": "dex",
            "name": "Acrobatics",
            "proficient": false
        },
        {
            "abilityName": "wis",
            "name": "Animal Handling",
            "proficient": false
        },
        {
            "abilityName": "int",
            "name": "Arcana",
            "proficient": false
        },
        {
            "abilityName": "str",
            "name": "Athletics",
            "proficient": false
        },
        {
            "abilityName": "cha",
            "name": "Deception",
            "proficient": false
        },
        {
            "abilityName": "int",
            "name": "History",
            "proficient": false
        },
        {
            "abilityName": "wis",
            "name": "Insight",
            "proficient": false
        },
        {
            "abilityName": "cha",
            "name": "Intimidation",
            "proficient": false
        },
        {
            "abilityName": "int",
            "name": "Investigation",
            "proficient": false
        },
        {
            "abilityName": "wis",
            "name": "Medicine",
            "proficient": true
        },
        {
            "abilityName": "int",
            "name": "Nature",
            "proficient": false
        },
        {
            "abilityName": "wis",
            "name": "Perception",
            "proficient": false
        },
        {
            "abilityName": "cha",
            "name": "Performance",
            "proficient": false
        },
        {
            "abilityName": "cha",
            "name": "Persuasion",
            "proficient": false
        },
        {
            "abilityName": "int",
            "name": "Religion",
            "proficient": true
        },
        {
            "abilityName": "dex",
            "name": "Sleight of Hand",
            "proficient": false
        },
        {
            "abilityName": "dex",
            "name": "Stealth",
            "proficient": false
        },
        {
            "abilityName": "wis",
            "name": "Survival",
            "proficient": false
        }
    ],
    "speed": 30,
    "spellFilters": [
        "Known"
    ],
    "spellSlots": [
        {
            "max": 3,
            "remaining": 3
        },
        {
            "max": 0,
            "remaining": 0
        },
        {
            "max": 0,
            "remaining": 0
        },
        {
            "max": 0,
            "remaining": 0
        },
        {
            "max": 0,
            "remaining": 0
        },
        {
            "max": 0,
            "remaining": 0
        },
        {
            "max": 0,
            "remaining": 0
        },
        {
            "max": 0,
            "remaining": 0
        }
    ],
    "spellcastingAbility": "wis",
    "spells": [
        {
            "canCastAtHigherLevel": true,
            "castingTime": "1 Action",
            "components": [
                "V",
                "S"
            ],
            "damage": [
                {
                    "abilityName": "spl",
                    "dice": "1d8",
                    "type": "Healing"
                }
            ],
            "description": "A creature you touch regains a number of hit points equal to 1d8 + your spellcasting ability modifier. This spell has no effect on undead or constructs.\n\nAt Higher Levels. When you cast this spell using a spell slot of 2nd level or higher, the healing increases by 1d8 for each slot level above 1st",
            "duration": "Instantaneous",
            "higherLevelDescription": "When you cast this spell using a spell slot of 2nd level or higher, the healing increases by 1d8 for each slot level above 1st",
            "higherLevels": [
                {
                    "applyAtLevels": [
                        2
                    ],
                    "damage": {
                        "abilityName": "spl",
                        "dice": "1d8",
                        "type": "Healing"
                    },
                    "type": "per-slot"
                }
            ],
            "level": 1,
            "name": "Cure Wounds",
            "range": "Touch",
            "savingThrow": {
            },
            "school": "Evocation",
            "tags": [
                "Artificer",
                "Bard",
                "Cleric",
                "Druid",
                "Paladin",
                "Ranger"
            ]
        }
    ],
    "systemKey": "5e",
    "textBlocks": [
        {
            "textBlocks": [
                {
                    "body": "The acolyte is a 1st-level spellcaster. Its spellcasting ability is Wisdom (spell save DC 12, +4 to hit with spell attacks). The acolyte has following cleric spells prepared:\nCantrips (at will): light, sacred flame, thaumaturgy\n1st level (3 slots): bless, cure wounds, sanctuary",
                    "title": "Spellcasting"
                }
            ],
            "title": "Abilities"
        }
    ],
    "type": "Humanoid",
    "typeTags": [
        "Any Race"
    ]
}
```

## Importing Multiple NPCs

To import multiple NPCs, create a JSON file with an object that contains a `characters` property that contains an array of `Character` objects.

| Field | Type | Description |
| ----- | ---- | ----------- |
| `characters` | `Character[]` | An array of `Character` objects. |

```json
{
  characters: [
    {
      name: "Acolyte"
    },
    {
      name: "Adept"
    }
  ]
}
```

```json
{
  characters: [
    {
      name: "Acolyte"
    },
    {
      name: "Cultist"
    }
  ]
}
```
