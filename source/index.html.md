---
title: Alchemy Developer Documentation

language_tabs: # must be one of https://git.io/vQNgJ
  - json

toc_footers:
  - <a href='https://github.com/alchemyrpg/slate'>❤️ Open Source</a>

includes:
  - ogl

search: true

code_clipboard: true

meta:
  - name: description
    content: Alchemy Developer Documentation
---

# Introduction

Welcome to the Alchemy developer documentation! On this page, you will find all of the information you need to integrate with Alchemy, including guides, API references, and more.

This documentation is open source. Please feel free to [open an issue](https://github.com/alchemyrpg/slate/issues/new?assignees=&labels=&template=bug.md) or [submit a pull request](https://github.com/alchemyrpg/slate/pulls) if you find any errors in the documentation or would like to add anything.

# Character Import

Alchemy Unlimited provides the ability to import NPCs into any universe that the user can edit. Today, this is a file-based import process, but we may open up an API for this in the future.

## Importing a single NPC

```json
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
            "savingThrow": {}
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
  "hitDice": "2d8",
  "imageUri": "https://cdn.alchemyrpg.com/app-assets/humanoid-token.svg",
  "initiativeBonus": 0,
  "isNPC": true,
  "isSpellcaster": true,
  "movementModes": [
    {
      "distance": 30,
      "mode": "Walking"
    }
  ],
  "name": "Acolyte",
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
  "spellFilters": ["Known"],
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
      "components": ["V", "S"],
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
          "applyAtLevels": [2],
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
      "savingThrow": {},
      "school": "Evocation",
      "tags": ["Artificer", "Bard", "Cleric", "Druid", "Paladin", "Ranger"]
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
  "typeTags": ["Any Race"],
  "trackers": [
    {
      "color": "Yellow",
      "max": 355000,
      "name": "XP",
      "type": "Bar",
      "value": 900
    },
    {
      "color": "Green",
      "max": 20,
      "name": "HP",
      "type": "Bar",
      "value": 20
    }
  ]
}
```

To import a single NPC, create a JSON file with a single [`Character`](#character) object in it. You can find more examples of single-character imports in the [alchemyrpg/5e-srd](https://github.com/alchemyrpg/5e-srd) repository.

## Importing multiple NPCs

```json
{
  "characters": [
    {
      "abilityScores": [
        {
          "name": "str",
          "value": 26
        },
        {
          "name": "dex",
          "value": 22
        },
        {
          "name": "con",
          "value": 26
        },
        {
          "name": "int",
          "value": 25
        },
        {
          "name": "wis",
          "value": 25
        },
        {
          "name": "cha",
          "value": 30
        }
      ],
      "actions": [
        {
          "description": "Melee Weapon Attack: +15 to hit, reach 5 ft., one target. Hit: 22 (4d6 + 8) slashing damage plus 27 (6d8) radiant damage.",
          "name": "Greatsword",
          "sortOrder": 0,
          "steps": [
            {
              "attack": {
                "ability": "str",
                "crit": 20,
                "damageRolls": [
                  {
                    "abilityName": "str",
                    "dice": "4d6",
                    "type": "Slashing"
                  },
                  {
                    "abilityName": "str",
                    "dice": "6d8",
                    "type": "Radiant"
                  }
                ],
                "isProficient": true,
                "isRanged": false,
                "name": "Greatsword",
                "rollsAttack": true,
                "savingThrow": {}
              },
              "journalCommand": {},
              "skillCheck": {},
              "type": "custom-attack"
            }
          ]
        },
        {
          "description": "Ranged Weapon Attack: +13 to hit, range 150/600 ft., one target. Hit: 15 (2d8 + 6) piercing damage plus 27 (6d8) radiant damage. If the target is a creature that has 100 hit points or fewer, it must succeed on a DC 15 Constitution saving throw or die.",
          "name": "Slaying Longbow",
          "sortOrder": 1,
          "steps": [
            {
              "attack": {
                "ability": "dex",
                "crit": 20,
                "damageRolls": [
                  {
                    "abilityName": "dex",
                    "dice": "2d8",
                    "type": "Piercing"
                  },
                  {
                    "dice": "6d8",
                    "type": "Radiant"
                  }
                ],
                "isProficient": true,
                "isRanged": true,
                "longRange": 600,
                "name": "Slaying Longbow",
                "range": 150,
                "rollsAttack": true,
                "savingThrow": {
                  "abilityName": "CON",
                  "difficultyClass": 15
                }
              },
              "journalCommand": {},
              "skillCheck": {},
              "type": "custom-attack"
            }
          ]
        },
        {
          "description": "The solar emits magical, divine energy. Each creature of its choice in a 10-foot radius must make a DC 23 Dexterity saving throw, taking 14 (4d6) fire damage plus 14 (4d6) radiant damage on a failed save, or half as much damage on a successful one.",
          "name": "Searing Burst (Costs 2 Actions)",
          "sortOrder": 2,
          "steps": [
            {
              "attack": {
                "crit": 20,
                "damageRolls": [
                  {
                    "dice": "4d6",
                    "type": "Fire"
                  },
                  {
                    "dice": "4d6",
                    "type": "Radiant"
                  }
                ],
                "isProficient": true,
                "isRanged": false,
                "name": "Searing Burst (Costs 2 Actions)",
                "rollsAttack": false,
                "savingThrow": {
                  "abilityName": "dex",
                  "difficultyClass": 23
                }
              },
              "journalCommand": {},
              "skillCheck": {},
              "type": "custom-attack"
            }
          ]
        },
        {
          "description": "The solar targets one creature it can see within 30 feet of it. If the target can see it, the target must succeed on a DC 15 Constitution saving throw or be blinded until magic such as the lesser restoration spell removes the blindness.",
          "name": "Blinding Gaze (Costs 3 Actions)",
          "sortOrder": 3,
          "steps": [
            {
              "attack": {
                "crit": 20,
                "isProficient": true,
                "isRanged": false,
                "name": "Blinding Gaze (Costs 3 Actions)",
                "rollsAttack": false,
                "savingThrow": {
                  "abilityName": "CON",
                  "difficultyClass": 15
                }
              },
              "journalCommand": {},
              "skillCheck": {},
              "type": "custom-attack"
            }
          ]
        }
      ],
      "alignment": "Lawful Good",
      "armorClass": 21,
      "armorType": "Natural Armor",
      "challengeRating": "21",
      "classes": [
        {
          "class": "Monster",
          "level": 1
        }
      ],
      "conditionImmunities": [
        "Charmed",
        "Exhaustion",
        "Frightened",
        "Poisoned",
        "Prone"
      ],
      "currentHp": 243,
      "damageImmunities": [
        {
          "damageType": "Necrotic"
        },
        {
          "damageType": "Poison"
        }
      ],
      "damageResistances": [
        {
          "damageType": "Radiant"
        },
        {
          "condition": "Nonmagical",
          "damageType": "Bludgeoning"
        },
        {
          "condition": "Nonmagical",
          "damageType": "Piercing"
        },
        {
          "condition": "Nonmagical",
          "damageType": "Slashing"
        }
      ],
      "exp": 33000,
      "hitDice": "18d10+144",
      "imageUri": "https://cdn.alchemyrpg.com/app-assets/celestial-token.svg",
      "initiativeBonus": 0,
      "isNPC": true,
      "isSpellcaster": true,
      "maxHp": 243,
      "movementModes": [
        {
          "distance": 50,
          "mode": "Walking"
        },
        {
          "distance": 150,
          "mode": "Fly"
        }
      ],
      "name": "Solar",
      "proficiencies": [
        {
          "name": "Intelligence",
          "type": "save"
        },
        {
          "name": "Wisdom",
          "type": "save"
        },
        {
          "name": "Charisma",
          "type": "save"
        },
        {
          "name": "All",
          "type": "language"
        },
        {
          "name": "telepathy 120 ft.",
          "type": "language"
        }
      ],
      "proficiencyBonus": 7,
      "race": "NPC",
      "senses": [
        {
          "distance": 120,
          "name": "Truesight"
        }
      ],
      "size": "Large",
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
          "proficient": false
        },
        {
          "abilityName": "int",
          "name": "Nature",
          "proficient": false
        },
        {
          "abilityName": "wis",
          "name": "Perception",
          "proficient": true
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
          "proficient": false
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
      "spellFilters": ["Known"],
      "spellSlots": [
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
      "spellcastingAbility": "cha",
      "spells": [
        {
          "castingTime": "1 Action",
          "components": ["V", "S"],
          "description": "For the duration, you know if there is an aberration, celestial, elemental, fey, fiend, or undead within 30 feet of you, as well as where the creature is located. Similarly, you know if there is a place or object within 30 feet of you that has been magically consecrated or desecrated.\n\nThe spell can penetrate most barriers, but it is blocked by 1 foot of stone, 1 inch of common metal, a thin sheet of lead, or 3 feet of wood or dirt.",
          "duration": "Up to 10 minutes",
          "level": 1,
          "name": "Detect Evil and Good",
          "range": "Self",
          "requiresConcentration": true,
          "savingThrow": {},
          "school": "Divination",
          "tags": ["Cleric", "Paladin"]
        },
        {
          "canCastAtHigherLevel": true,
          "castingTime": "1 Action",
          "components": ["V", "S", "M"],
          "description": "A creature you touch becomes invisible until the spell ends. Anything the target is wearing or carrying is invisible as long as it is on the target's person. The spell ends for a target that attacks or casts a spell.\n\nAt Higher Levels. When you cast this spell using a spell slot of 3rd level or higher, you can target one additional creature for each slot level above 2nd.",
          "duration": "Up to 1 hour",
          "higherLevelDescription": "When you cast this spell using a spell slot of 3rd level or higher, you can target one additional creature for each slot level above 2nd.",
          "level": 2,
          "materials": "an eyelash encased in gum arabic",
          "name": "Invisibility",
          "range": "Touch",
          "requiresConcentration": true,
          "savingThrow": {},
          "school": "Illusion",
          "tags": ["Artificer", "Bard", "Sorcerer", "Warlock", "Wizard"]
        },
        {
          "canBeCastAsRitual": true,
          "castingTime": "1 minute",
          "components": ["V", "S", "M"],
          "description": "You contact your deity or a divine proxy and ask up to three questions that can be answered with a yes or no. You must ask your questions before the spell ends. You receive a correct answer for each question.\n\nDivine beings aren't necessarily omniscient, so you might receive \"unclear\" as an answer if a question pertains to information that lies beyond the deity's knowledge. In a case where a one-word answer could be misleading or contrary to the deity's interests, the DM might offer a short phrase as an answer instead.\n\nIf you cast the spell two or more times before finishing your next long rest, there is a cumulative 25 percent chance for each casting after the first that you get no answer. The DM makes this roll in secret.",
          "duration": "1 minute",
          "level": 5,
          "materials": "incense and a vial of holy or unholy water",
          "name": "Commune",
          "range": "Self",
          "savingThrow": {},
          "school": "Divination",
          "tags": ["Cleric"]
        },
        {
          "castingTime": "1 Action",
          "components": ["V", "S"],
          "damage": [
            {
              "dice": "6d10",
              "type": "Slashing"
            }
          ],
          "description": "You create a vertical wall of whirling, razor-sharp blades made of magical energy. The wall appears within range and lasts for the duration. You can make a straight wall up to 100 feet long, 20 feet high, and 5 feet thick, or a ringed wall up to 60 feet in diameter, 20 feet high, and 5 feet thick. The wall provides three-quarters cover to creatures behind it, and its space is difficult terrain.\n\nWhen a creature enters the wall's area for the first time on a turn or starts its turn there, the creature must make a Dexterity saving throw. On a failed save, the creature takes 6d10 slashing damage. On a successful save, the creature takes half as much damage.",
          "duration": "Up to 10 minutes",
          "level": 6,
          "name": "Blade Barrier",
          "range": "90 ft.",
          "requiresConcentration": true,
          "rollsAttack": false,
          "savingThrow": {
            "abilityName": "dex"
          },
          "school": "Evocation",
          "tags": ["Cleric"]
        },
        {
          "castingTime": "10 minutes",
          "components": ["V", "M", "S"],
          "description": "You take control of the weather within 5 miles of you for the duration. You must be outdoors to cast this spell. Moving to a place where you don't have a clear path to the sky ends the spell early.\n\nWhen you cast the spell, you change the current weather conditions, which are determined by the DM based on the climate and season. You can change precipitation, temperature, and wind. It takes 1d4 × 10 minutes for the new conditions to take effect. Once they do so, you can change the conditions again. When the spell ends, the weather gradually returns to normal.\n\nWhen you change the weather conditions, find a current condition on the following tables and change its stage by one, up or down. When changing the wind, you can change its direction.\n\nPrecipitation\nStage\tCondition\n1\t        Clear\n2\t        Light clouds\n3\t       Overcast or ground fog\n4\t        Rain, hail, or snow\n5\t        Torrential rain, driving hail, or blizzard\n\nTemperature\nStage\tCondition\n1\t        Unbearable heat\n2\t        Hot\n3\t        Warm\n4\t        Cool\n5\t        Cold\n6\t        Arctic cold\n\nWind\nStage\tCondition\n1\t        Calm\n2\t        Moderate wind\n3\t        Strong wind\n4\t        Gale\n5\t        Storm",
          "duration": "Up to 8 hours",
          "level": 8,
          "materials": "burning incense and bits of earth and wood mixed in water",
          "name": "Control Weather",
          "range": "Self (5-mile radius)",
          "requiresConcentration": true,
          "savingThrow": {},
          "school": "Transmutation",
          "tags": ["Cleric", "Druid", "Wizard"]
        },
        {
          "castingTime": "1 Action",
          "components": ["V", "S", "M"],
          "description": "Shimmering energy surrounds and protects you from fey, undead, and creatures originating from beyond the Material Plane. For the duration, celestials, elementals, fey, fiends, and undead have disadvantage on attack rolls against you.\n\nYou can end the spell early by using either of the following special functions.\n\nBreak Enchantment. As your action, you touch a creature you can reach that is charmed, frightened, or possessed by a celestial, an elemental, a fey, a fiend, or an undead. The creature you touch is no longer charmed, frightened, or possessed by such creatures.\n\nDismissal. As your action, make a melee spell attack against a celestial, an elemental, a fey, a fiend, or an undead you can reach. On a hit, you attempt to drive the creature back to its home plane. The creature must succeed on a Charisma saving throw or be sent back to its home plane (if it isn't there already). If they aren't on their home plane, undead are sent to the Shadowfell, and fey are sent to the Feywild.",
          "duration": "Up to 1 minute",
          "level": 5,
          "materials": "holy water or powdered silver and iron",
          "name": "Dispel Evil and Good",
          "range": "Self",
          "requiresConcentration": true,
          "savingThrow": {},
          "school": "Abjuration",
          "tags": ["Cleric", "Paladin"]
        },
        {
          "castingTime": "1 hour",
          "components": ["V", "S", "M"],
          "description": "You touch a dead creature that has been dead for no more than a century, that didn't die of old age, and that isn't undead. If its soul is free and willing, the target returns to life with all its hit points.\n\nThis spell neutralizes any poisons and cures normal diseases afflicting the creature when it died. It doesn't, however, remove magical diseases, curses, and the like; if such effects aren't removed prior to casting the spell, they afflict the target on its return to life.\n\nThis spell closes all mortal wounds and restores any missing body parts.\n\nComing back from the dead is an ordeal. The target takes a −4 penalty to all attack rolls, saving throws, and ability checks. Every time the target finishes a long rest, the penalty is reduced by 1 until it disappears.\n\nCasting this spell to restore life to a creature that has been dead for one year or longer taxes you greatly. Until you finish a long rest, you can't cast spells again, and you have disadvantage on all attack rolls, ability checks, and saving throws.",
          "duration": "Instantaneous",
          "level": 7,
          "materials": "a diamond worth at least 1,000 gp, which the spell consumes",
          "name": "Resurrection",
          "range": "Touch",
          "savingThrow": {},
          "school": "Necromancy",
          "tags": ["Bard", "Cleric"]
        }
      ],
      "textBlocks": [
        {
          "title": "Class Features"
        },
        {
          "title": "Racial Traits"
        },
        {
          "title": "Feats"
        },
        {
          "textBlocks": [{}, {}],
          "title": "Background"
        },
        {
          "textBlocks": [
            {
              "title": "Personality Traits"
            },
            {
              "title": "Ideals"
            },
            {
              "title": "Bonds"
            },
            {
              "title": "Flaws"
            }
          ],
          "title": "Characteristics"
        },
        {
          "textBlocks": [{}],
          "title": "Appearance"
        },
        {
          "title": "Organizations"
        },
        {
          "title": "Allies"
        },
        {
          "title": "Enemies"
        },
        {
          "textBlocks": [{}],
          "title": "Backstory"
        },
        {
          "textBlocks": [{}],
          "title": "Other"
        },
        {
          "textBlocks": [
            {
              "body": "The solar's weapon attacks are magical. When the solar hits with any weapon, the weapon deals an extra 6d8 radiant damage (included in the attack).",
              "title": "Angelic Weapons"
            },
            {
              "body": "The solar knows if it hears a lie.\n",
              "title": "Divine Awareness"
            },
            {
              "body": "The solar's spellcasting ability is Charisma (spell save DC 25). It can innately cast the following spells, requiring no material components:\n\nAt will: detect evil and good, invisibility (self only)\n\n3/day each: blade barrier, dispel evil and good, resurrection\n\n1/day each: commune, control weather",
              "title": "Innate Spellcasting"
            },
            {
              "body": "The solar has advantage on saving throws against spells and other magical effects.",
              "title": "Magic Resistance"
            },
            {
              "body": "The solar makes two greatsword attacks.",
              "title": "Multiattack"
            },
            {
              "body": "The solar releases its greatsword to hover magically in an unoccupied space within 5 feet of it. If the solar can see the sword, the solar can mentally command it as a bonus action to fly up to 50 feet and either make one attack against a target or return to the solar's hands. If the hovering sword is targeted by any effect, the solar is considered to be holding it. The hovering sword falls if the solar dies.\n",
              "title": "Flying Sword"
            },
            {
              "body": "The solar touches another creature. The target magically regains 40 (8d8 + 4) hit points and is freed from any curse, disease, poison, blindness, or deafness.",
              "title": "Healing Touch (4/Day)"
            },
            {
              "body": "The solar can take 3 legendary actions, choosing from the options below. Only one legendary action can be used at a time and only at the end of another creature's turn. The solar regains spent legendary actions at the start of its turn.\n\nTeleport. The solar magically teleports, along with any equipment it is wearing or carrying, up to 120 feet to an unoccupied space it can see.\n\nSearing Burst (Costs 2 Actions). The solar emits magical, divine energy. Each creature of its choice in a 10-foot radius must make a DC 23 Dexterity saving throw, taking 14 (4d6) fire damage plus 14 (4d6) radiant damage on a failed save, or half as much damage on a successful one.\n\nBlinding Gaze (Costs 3 Actions). The solar targets one creature it can see within 30 feet of it. If the target can see it, the target must succeed on a DC 15 Constitution saving throw or be blinded until magic such as the lesser restoration spell removes the blindness.",
              "title": "Legendary Actions"
            }
          ],
          "title": "Abilities"
        }
      ],
      "type": "Celestial",
      "trackers": [
        {
          "color": "Yellow",
          "max": 355000,
          "name": "XP",
          "type": "Bar",
          "value": 900
        },
        {
          "color": "Green",
          "max": 20,
          "name": "HP",
          "type": "Bar",
          "value": 20
        }
      ]
    },
    {
      "abilityScores": [
        {
          "name": "str",
          "value": 30
        },
        {
          "name": "dex",
          "value": 11
        },
        {
          "name": "con",
          "value": 30
        },
        {
          "name": "int",
          "value": 3
        },
        {
          "name": "wis",
          "value": 11
        },
        {
          "name": "cha",
          "value": 11
        }
      ],
      "actions": [
        {
          "description": "Melee Weapon Attack: +19 to hit, reach 10 ft., one target. Hit: 36 (4d12 + 10) piercing damage. If the target is a creature, it is grappled (escape DC 20). Until this grapple ends, the target is restrained, and the tarrasque can't bite another target.",
          "name": "Bite",
          "sortOrder": 0,
          "steps": [
            {
              "attack": {
                "ability": "str",
                "crit": 20,
                "damageRolls": [
                  {
                    "abilityName": "str",
                    "dice": "4d12",
                    "type": "Piercing"
                  }
                ],
                "isProficient": true,
                "isRanged": false,
                "name": "Bite",
                "rollsAttack": true,
                "savingThrow": {}
              },
              "journalCommand": {},
              "skillCheck": {},
              "type": "custom-attack"
            }
          ]
        },
        {
          "description": "Melee Weapon Attack: +19 to hit, reach 15 ft., one target. Hit: 28 (4d8 + 10) slashing damage.",
          "name": "Claw",
          "sortOrder": 1,
          "steps": [
            {
              "attack": {
                "ability": "str",
                "crit": 20,
                "damageRolls": [
                  {
                    "abilityName": "str",
                    "dice": "4d8",
                    "type": "Slashing"
                  }
                ],
                "isProficient": true,
                "isRanged": false,
                "name": "Claw",
                "rollsAttack": true,
                "savingThrow": {}
              },
              "journalCommand": {},
              "skillCheck": {},
              "type": "custom-attack"
            }
          ]
        },
        {
          "description": "Melee Weapon Attack: +19 to hit, reach 10 ft., one target. Hit: 32 (4d10 + 10) piercing damage.",
          "name": "Horns",
          "sortOrder": 2,
          "steps": [
            {
              "attack": {
                "ability": "str",
                "crit": 20,
                "damageRolls": [
                  {
                    "abilityName": "str",
                    "dice": "4d10",
                    "type": "Piercing"
                  }
                ],
                "isProficient": true,
                "isRanged": false,
                "name": "Horns",
                "rollsAttack": true,
                "savingThrow": {}
              },
              "journalCommand": {},
              "skillCheck": {},
              "type": "custom-attack"
            }
          ]
        },
        {
          "description": "Melee Weapon Attack: +19 to hit, reach 20 ft., one target. Hit: 24 (4d6 + 10) bludgeoning damage. If the target is a creature, it must succeed on a DC 20 Strength saving throw or be knocked prone.",
          "name": "Tail",
          "sortOrder": 3,
          "steps": [
            {
              "attack": {
                "ability": "str",
                "crit": 20,
                "damageRolls": [
                  {
                    "abilityName": "str",
                    "dice": "4d6",
                    "type": "Bludgeoning"
                  }
                ],
                "isProficient": true,
                "isRanged": false,
                "name": "Tail",
                "rollsAttack": true,
                "savingThrow": {}
              },
              "journalCommand": {},
              "skillCheck": {},
              "type": "custom-attack"
            }
          ]
        },
        {
          "description": "Each creature of the tarrasque's choice within 120 feet of it and aware of it must succeed on a DC 17 Wisdom saving throw or become frightened for 1 minute. A creature can repeat the saving throw at the end of each of its turns, with disadvantage if the tarrasque is within line of sight, ending the effect on itself on a success. If a creature's saving throw is successful or the effect ends for it, the creature is immune to the tarrasque's Frightful Presence for the next 24 hours.",
          "name": "Frightful Presence",
          "sortOrder": 4,
          "steps": [
            {
              "attack": {
                "crit": 20,
                "isProficient": true,
                "isRanged": false,
                "name": "Frightful Presence",
                "rollsAttack": false,
                "savingThrow": {
                  "abilityName": "wis",
                  "difficultyClass": 17
                }
              },
              "journalCommand": {},
              "skillCheck": {},
              "type": "custom-attack"
            }
          ]
        },
        {
          "description": " The tarrasque makes one bite attack against a Large or smaller creature it is grappling. If the attack hits, the target takes the bite's damage, the target is swallowed, and the grapple ends. While swallowed, the creature is blinded and restrained, it has total cover against attacks and other effects outside the tarrasque, and it takes 56 (16d6) acid damage at the start of each of the tarrasque's turns.\n   If the tarrasque takes 60 damage or more on a single turn from a creature inside it, the tarrasque must succeed on a DC 20 Constitution saving throw at the end of that turn or regurgitate all swallowed creatures, which fall prone in a space within 10 feet of the tarrasque. If the tarrasque dies, a swallowed creature is no longer restrained by it and can escape from the corpse by using 30 feet of movement, exiting prone.",
          "name": "Swallow",
          "sortOrder": 5,
          "steps": [
            {
              "attack": {
                "crit": 20,
                "damageRolls": [
                  {
                    "dice": "16d6",
                    "type": "Acid"
                  }
                ],
                "isProficient": true,
                "isRanged": false,
                "name": "Swallow",
                "rollsAttack": false,
                "savingThrow": {
                  "abilityName": "CON",
                  "difficultyClass": 17
                }
              },
              "journalCommand": {},
              "skillCheck": {},
              "type": "custom-attack"
            }
          ]
        }
      ],
      "alignment": "Unaligned",
      "armorClass": 25,
      "armorType": "Natural Armor",
      "challengeRating": "30",
      "classes": [
        {
          "class": "Monster",
          "level": 1
        }
      ],
      "conditionImmunities": ["Charmed", "Frightened", "Paralyzed", "Poisoned"],
      "currentHp": 676,
      "damageImmunities": [
        {
          "damageType": "Fire"
        },
        {
          "damageType": "Poison"
        },
        {
          "condition": "Nonmagical",
          "damageType": "Bludgeoning"
        },
        {
          "condition": "Nonmagical",
          "damageType": "Piercing"
        },
        {
          "condition": "Nonmagical",
          "damageType": "Slashing"
        }
      ],
      "exp": 155000,
      "hitDice": "33d20+330",
      "imageUri": "https://cdn.alchemyrpg.com/app-assets/monstrosity-token.svg",
      "initiativeBonus": 0,
      "isNPC": true,
      "maxHp": 676,
      "movementModes": [
        {
          "distance": 40,
          "mode": "Walking"
        }
      ],
      "name": "Tarrasque",
      "proficiencies": [
        {
          "name": "Intelligence",
          "type": "save"
        },
        {
          "name": "Wisdom",
          "type": "save"
        },
        {
          "name": "Charisma",
          "type": "save"
        }
      ],
      "proficiencyBonus": 9,
      "race": "NPC",
      "senses": [
        {
          "distance": 120,
          "name": "Blindsight"
        }
      ],
      "size": "Gargantuan",
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
          "proficient": false
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
          "proficient": false
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
      "textBlocks": [
        {
          "title": "Class Features"
        },
        {
          "title": "Racial Traits"
        },
        {
          "title": "Feats"
        },
        {
          "textBlocks": [{}, {}],
          "title": "Background"
        },
        {
          "textBlocks": [
            {
              "title": "Personality Traits"
            },
            {
              "title": "Ideals"
            },
            {
              "title": "Bonds"
            },
            {
              "title": "Flaws"
            }
          ],
          "title": "Characteristics"
        },
        {
          "textBlocks": [{}],
          "title": "Appearance"
        },
        {
          "title": "Organizations"
        },
        {
          "title": "Allies"
        },
        {
          "title": "Enemies"
        },
        {
          "textBlocks": [{}],
          "title": "Backstory"
        },
        {
          "textBlocks": [{}],
          "title": "Other"
        },
        {
          "textBlocks": [
            {
              "body": "If the tarrasque fails a saving throw, it can choose to succeed instead.",
              "title": "Legendary Resistance (3/Day) "
            },
            {
              "body": "The tarrasque has advantage on saving throws against spells and other magical effects.",
              "title": "Magic Resistance"
            },
            {
              "body": "Any time the tarrasque is targeted by a magic missile spell, a line spell, or a spell that requires a ranged attack roll, roll a d6. On a 1 to 5, the tarrasque is unaffected. On a 6, the tarrasque is unaffected, and the effect is reflected back at the caster as though it originated from the tarrasque, turning the caster into the target.",
              "title": "Reflective Carapace "
            },
            {
              "body": " The tarrasque deals double damage to objects and structures.",
              "title": "Siege Monster"
            },
            {
              "body": "The tarrasque can take 3 legendary actions, choosing from the options below. Only one legendary action can be used at a time and only at the end of another creature's turn. The tarrasque regains spent legendary actions at the start of its turn.\n\nAttack. The tarrasque makes one claw attack or tail attack.\n\nMove. The tarrasque moves up to half its speed.\n\nChomp (Costs 2 Actions). The tarrasque makes one bite attack or uses its Swallow.",
              "title": "Legendary Actions"
            }
          ],
          "title": "Abilities"
        }
      ],
      "type": "Monstrosity",
      "typeTags": ["Titan"],
      "trackers": [
        {
          "color": "Yellow",
          "max": 355000,
          "name": "XP",
          "type": "Bar",
          "value": 900
        },
        {
          "color": "Green",
          "max": 20,
          "name": "HP",
          "type": "Bar",
          "value": 20
        }
      ]
    }
  ]
}
```

To import multiple NPCs, create a JSON file with an object that contains a `characters` property that contains an array of [`Character`](#character) objects. You can find more examples of bulk character imports in the [alchemyrpg/5e-srd](https://github.com/alchemyrpg/5e-srd) repository.

| Attribute    | Type                        | Description                                    |
| ------------ | --------------------------- | ---------------------------------------------- |
| `characters` | [`Character[]`](#character) | An array of [`Character`](#character) objects. |

# API Documentation

## AbilityScore

```json
{
  "name": "str",
  "value": 11
}
```

| Attribute | Type     | Description                                                                                                                        |
| --------- | -------- | ---------------------------------------------------------------------------------------------------------------------------------- |
| `name`    | `string` | The name of the ability score. For 5e, we use the abbreviation: str, dex, con, int, wis, cha.                                      |
| `value`   | `number` | The ability score's value. The modifier, if appropriate for the game system, will be calculated by the game system implementation. |

## Action

```json
{
  "description": "Melee Weapon Attack: +11 to hit, reach 10 ft., one target. Hit: 17 (2d10 + 6) piercing damage plus 7 (2d6) poison damage.",
  "name": "Bite",
  "sortOrder": 0,
  "steps": [
    {
      "attack": {
        "ability": "str",
        "crit": 20,
        "damageRolls": [
          {
            "abilityName": "str",
            "dice": "2d6",
            "type": "Piercing"
          },
          {
            "dice": "2d6",
            "type": "Poison"
          }
        ],
        "isProficient": true,
        "isRanged": false,
        "name": "Bite",
        "rollsAttack": true,
        "savingThrow": {}
      },
      "journalCommand": {},
      "skillCheck": {},
      "type": "custom-attack"
    }
  ]
}
```

| Attribute     | Type                          | Description                                                                                                                                                                             |
| ------------- | ----------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `description` | `string`                      | The description of the action, visible to other players when this action is rolled into the journal.                                                                                    |
| `name`        | `string`                      | The name of the action. This is visible in the actions panel when playing the character and is also used as the title for the card displayed in the journal when this action is rolled. |
| `sortOrder`   | `number`                      | The order in which this action should be displayed in the actions panel.                                                                                                                |
| `steps`       | [`ActionStep[]`](#actionstep) | An array of [`ActionStep`](#actionstep) objects that describe the steps to take when rolling this action.                                                                               |

## ActionStep

```json
{
  "attack": {
    "crit": 20,
    "isProficient": true,
    "isRanged": false,
    "name": "Frightful Presence",
    "rollsAttack": false,
    "savingThrow": {
      "abilityName": "wis",
      "difficultyClass": 16
    }
  },
  "journalCommand": {},
  "skillCheck": {},
  "type": "custom-attack"
}
```

| Attribute         | Type                                                    | Description                                                                                                                      |
| ----------------- | ------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| `type`            | `string`                                                | The type of action step. Supported values are: `message`, `journal-command`, `custom-dice-roll`, `custom-attack`, `skill-check`. |
| ` journalCommand` | [`ActionStepJournalCommand`](#actionstepjournalcommand) | If this is a `journal-command` ActionStep type, this contains the details of the command to execute.                             |
| `diceRoll`        | [`ActionStepDamage[]`](#actionstepdamage)               | If this is a `custom-dice-roll` ActionStep type, this is the array of dice to roll.                                              |
| `attack`          | [`ActionStepAttack`](#actionstepattack)                 | If this is a `custom-attack` ActionStep type, this is the attack to roll. This is only used by 5e characters.                    |
| `skillCheck`      | [`ActionStepSkillCheck`](#actionstepskillcheck)         | If this is a `skill-check` ActionStep type, this contains the details of the skill check.                                        |

## ActionStepAttack

```json
{
  "crit": 20,
  "isProficient": true,
  "isRanged": false,
  "name": "Frightful Presence",
  "rollsAttack": false,
  "savingThrow": {
    "abilityName": "wis",
    "difficultyClass": 16
  }
}
```

```json
{
  "ability": "str",
  "crit": 20,
  "damageRolls": [
    {
      "abilityName": "str",
      "dice": "2d8",
      "type": "Bludgeoning"
    }
  ],
  "isProficient": true,
  "isRanged": false,
  "name": "Tail",
  "rollsAttack": true
}
```

| Attribute      | Type                                      | Description                                                                                                                       |
| -------------- | ----------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| `ability`      | `string`                                  | The ability score to use for the attack roll.                                                                                     |
| `bonus`        | `number`                                  | The bonus to add to the attack roll.                                                                                              |
| `crit`         | `number`                                  | The number at which this attack is considered a critical hit.                                                                     |
| `damageRolls`  | [`ActionStepDamage[]`](#actionstepdamage) | An array of [`ActionStepDamage`](#actionstepdamage) objects that describe the damage to roll.                                     |
| `isProficient` | `boolean`                                 | Whether the character is proficient in the attack and thus whether to apply the character's proficiency bonus to the attack roll. |
| `isRanged`     | `boolean`                                 | Whether this is a ranged attack.                                                                                                  |
| `name`         | `string`                                  | The name of the attack.                                                                                                           |
| `range`        | `number`                                  | The range of the attack.                                                                                                          |
| `longRange`    | `number`                                  | The threshold for long range, or the point at which disadvantage is applied to the attack roll.                                   |
| `rollsAttack`  | `boolean`                                 | Whether this attack rolls an attack roll.                                                                                         |
| `savingThrow`  | [`SavingThrow`](#savingthrow)             | If this attack is a saving throw, this contains the details of the saving throw.                                                  |

## ActionStepDamage

```json
{
  "abilityName": "str",
  "dice": "4d6",
  "type": "Slashing"
}
```

| Attribute     | Type     | Description                                                     |
| ------------- | -------- | --------------------------------------------------------------- |
| `abilityName` | `string` | The ability score to use for the damage roll.                   |
| `bonus`       | `number` | An arbitrary bonus to add to the damage roll.                   |
| `dice`        | `string` | The dice to roll for the damage.                                |
| `type`        | `string` | The type of damage to be dealt (e.g. Slashing, Piercing, etc.). |

## ActionStepJournalCommand

```json
{
  "command": "/me",
  "args": "glances dubiously in your direction."
}
```

| Attribute | Type     | Description                                                                                            |
| --------- | -------- | ------------------------------------------------------------------------------------------------------ |
| `command` | `string` | The journal slash command to execute. Currently available commands are `/me`, `/roll`, and `/whisper`. |
| `args`    | `string` | The arguments to pass to the command.                                                                  |

## ActionStepSkillCheck

```json
{
  "rollModifier": "advantage",
  "skillName": "Acrobatics"
}
```

| Attribute      | Type     | Description                                                                                                 |
| -------------- | -------- | ----------------------------------------------------------------------------------------------------------- |
| `rollModifier` | `string` | The modifier to apply to the skill check. Currently available modifiers are `advantage` and `disadvantage`. |
| `skillName`    | `string` | The name of a skill present on the character to roll a skill check for.                                     |

## Character

```json
{
  "abilityScores": [
    {
      "name": "str",
      "value": 11
    },
    {
      "name": "dex",
      "value": 14
    },
    {
      "name": "con",
      "value": 12
    },
    {
      "name": "int",
      "value": 10
    },
    {
      "name": "wis",
      "value": 13
    },
    {
      "name": "cha",
      "value": 14
    }
  ],
  "actions": [
    {
      "description": "Melee or Ranged Weapon Attack: +4 to hit, reach 5 ft. or range 20/60 ft., one creature. Hit: 4 (1d4 + 2) piercing damage.",
      "name": "Dagger",
      "sortOrder": 0,
      "steps": [
        {
          "attack": {
            "ability": "dex",
            "crit": 20,
            "damageRolls": [
              {
                "abilityName": "dex",
                "dice": "1d4",
                "type": "Piercing"
              }
            ],
            "isProficient": true,
            "isRanged": false,
            "name": "Dagger",
            "savingThrow": {}
          },
          "journalCommand": {},
          "skillCheck": {},
          "type": "custom-attack"
        }
      ]
    },
    {
      "description": "Melee or Ranged Weapon Attack: +4 to hit, reach 5 ft. or range 20/60 ft., one creature. Hit: 4 (1d4 + 2) piercing damage.",
      "name": "Dagger (Thrown)",
      "sortOrder": 1,
      "steps": [
        {
          "attack": {
            "ability": "dex",
            "crit": 20,
            "damageRolls": [
              {
                "abilityName": "dex",
                "dice": "1d4",
                "type": "Piercing"
              }
            ],
            "isProficient": true,
            "isRanged": true,
            "longRange": 60,
            "name": "Dagger (Thrown)",
            "range": 20,
            "savingThrow": {}
          },
          "journalCommand": {},
          "skillCheck": {},
          "type": "custom-attack"
        }
      ]
    }
  ],
  "alignment": "Any Non-Good Alignment",
  "armorClass": 13,
  "armorType": "Leather Armor",
  "challengeRating": "2",
  "classes": [
    {
      "class": "Monster",
      "level": 1
    }
  ],
  "currentHp": 33,
  "exp": 450,
  "hitDice": "6d8+6",
  "imageUri": "https://cdn.alchemyrpg.com/app-assets/humanoid-token.svg",
  "initiativeBonus": 0,
  "isNPC": true,
  "isSpellcaster": true,
  "maxHp": 33,
  "movementModes": [
    {
      "distance": 30,
      "mode": "Walking"
    }
  ],
  "name": "Cult Fanatic",
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
      "proficient": true
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
      "proficient": false
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
      "proficient": true
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
  "spellFilters": ["Known"],
  "spellSlots": [
    {
      "max": 4,
      "remaining": 4
    },
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
      "name": "Sacred Flame"
    },
    {
      "name": "Thaumaturgy"
    },
    {
      "name": "Command"
    },
    {
      "name": "Shield of Faith"
    },
    {
      "name": "Inflict Wounds"
    },
    {
      "name": "Spiritual Weapon"
    },
    {
      "name": "Light"
    },
    {
      "name": "Hold Person"
    },
    {
      "name": "Sacred Flame"
    },
    {
      "name": "Thaumaturgy"
    },
    {
      "name": "Light"
    },
    {
      "name": "Command"
    },
    {
      "name": "Shield of Faith"
    },
    {
      "name": "Inflict Wounds"
    },
    {
      "name": "Hold Person"
    },
    {
      "name": "Spiritual Weapon"
    },
    {
      "canCastAtHigherLevel": true,
      "castingTime": "1 Action",
      "components": ["V", "S"],
      "damage": [
        {
          "dice": "6d6",
          "type": "Necrotic"
        }
      ],
      "description": "Make a melee spell attack against a creature you can reach. On a hit, the target takes 6d6 necrotic damage.\n\nWhen you cast this spell using a spell slot of 2nd level or higher, the damage increases by 1d10 for each slot level above 1st.",
      "duration": "Instantaneous",
      "higherLevelDescription": "When you cast this spell using a spell slot of 2nd level or higher, the damage increases by 1d10 for each slot level above 1st.",
      "higherLevels": [
        {
          "applyAtLevels": [2],
          "damage": {
            "dice": "1d10",
            "type": "Necrotic"
          },
          "type": "per-slot"
        }
      ],
      "level": 1,
      "name": "Custom Wound Inflictor",
      "range": "Touch",
      "rollsAttack": true,
      "savingThrow": {},
      "school": "Necromancy",
      "tags": ["Cleric"]
    }
  ],
  "textBlocks": [
    {
      "textBlocks": [
        {
          "body": "The fanatic has advantage on saving throws against being charmed or frightened.",
          "title": "Dark Devotion"
        },
        {
          "body": "The fanatic is a 4th-level spellcaster. Its spellcasting ability is Wisdom (spell save DC 11, +3 to hit with spell attacks). The fanatic has the following cleric spells prepared:\nCantrips (at will): light, sacred flame, thaumaturgy\n1st level (4 slots): command, inflict wounds, shield of faith\n2nd level (3 slots): hold person, spiritual weapon",
          "title": "Spellcasting"
        },
        {
          "body": "The fanatic makes two melee attacks.",
          "title": "Multiattack"
        }
      ],
      "title": "Abilities"
    }
  ],
  "type": "Humanoid",
  "typeTags": ["Any Race"],
  "trackers": [
    {
      "color": "Yellow",
      "max": 355000,
      "name": "XP",
      "type": "Bar",
      "value": 900
    },
    {
      "color": "Green",
      "max": 20,
      "name": "HP",
      "type": "Bar",
      "value": 20
    }
  ]
}
```

The [`Character`](#character) object represents a player or non-player character on Alchemy.

When creating a character for 5e, note that SRD spells can simply be an object with the `name` property set to the name of the spell rather than a full [`Spell`](#spell) object. If the spell name matches an existing SRD spell (case-insensitive), it will be added to the character.

| Attribute               | Type                                                        | Description                                                                                                                                                                                                                                                                                                                                |
| ----------------------- | ----------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `abilityScores`         | [`AbilityScore[]`](#abilityscore)                           | The character's ability scores.                                                                                                                                                                                                                                                                                                            |
| `actions`               | [`Action[]`](#action)                                       | The character's actions.                                                                                                                                                                                                                                                                                                                   |
| `age`                   | `string`                                                    | The character's age.                                                                                                                                                                                                                                                                                                                       |
| `alignment`             | `string`                                                    | The character's alignment.                                                                                                                                                                                                                                                                                                                 |
| `armorClass`            | `number`                                                    | The character's armor class including all bonuses.                                                                                                                                                                                                                                                                                         |
| `armorType`             | `string`                                                    | The character's armor type.                                                                                                                                                                                                                                                                                                                |
| `appearance`            | `string`                                                    | A long description of the character's appearance.                                                                                                                                                                                                                                                                                          |
| `challengeRating`       | `string`                                                    | A non-player character's challenge rating.                                                                                                                                                                                                                                                                                                 |
| `classes`               | [`Class[]`](#class)                                         | An array of character classes and their associated levels.                                                                                                                                                                                                                                                                                 |
| `conditionImmunities`   | `string[]`                                                  | A non-player character's condition immunities.                                                                                                                                                                                                                                                                                             |
| `copper`                | `number`                                                    | The number of copper coins carried by the character.                                                                                                                                                                                                                                                                                       |
| `currentHp`             | `number`                                                    | The character's current hit points.                                                                                                                                                                                                                                                                                                        |
| `damageImmunities`      | [`CharacterDamageAdjustment[]`](#characterdamageadjustment) | A non-player character's damage immunities.                                                                                                                                                                                                                                                                                                |
| `damageResistances`     | [`CharacterDamageAdjustment[]`](#characterdamageadjustment) | A non-player character's damage resistances.                                                                                                                                                                                                                                                                                               |
| `damageVulnerabilities` | [`CharacterDamageAdjustment[]`](#characterdamageadjustment) | A non-player character's damage vulnerabilities.                                                                                                                                                                                                                                                                                           |
| `description`           | Markdown `string`                                           | An [Alchemy-flavored markdown](https://app.alchemyrpg.com/universe/6260df75b0b47dc841b01d56/article/62faeeae89d4b645be22f85c) description of the character.                                                                                                                                                                                |
| `electrum`              | `number`                                                    | The number of electrum coins carried by the character.                                                                                                                                                                                                                                                                                     |
| `eyes`                  | `string`                                                    | The character's eye color.                                                                                                                                                                                                                                                                                                                 |
| `exp`                   | `number`                                                    | The amount of experience points that the character has earned.                                                                                                                                                                                                                                                                             |
| `gold`                  | `number`                                                    | The number of gold coins carried by the character.                                                                                                                                                                                                                                                                                         |
| `hair`                  | `string`                                                    | The character's hair color.                                                                                                                                                                                                                                                                                                                |
| `height`                | `string`                                                    | The character's height.                                                                                                                                                                                                                                                                                                                    |
| `hitDice`               | `string`                                                    | The character's hit dice.                                                                                                                                                                                                                                                                                                                  |
| `imageUri`              | `string`                                                    | A URI for the character's avatar or profile picture.                                                                                                                                                                                                                                                                                       |
| `initiativeBonus`       | `number`                                                    | The character's total initiative bonus.                                                                                                                                                                                                                                                                                                    |
| `isBackstoryPublic`     | `boolean`                                                   | Indicates whether the character's backstory should be visible to other players.                                                                                                                                                                                                                                                            |
| `isSpellcaster`         | `boolean`                                                   | Indicates whether this character is a spellcaster or not. This is used to trigger the display of spellcasting features in the UI.                                                                                                                                                                                                          |
| `legendary`             | `boolean`                                                   | Indicates whether this character is a legendary creature.                                                                                                                                                                                                                                                                                  |
| `maxHp`                 | `number`                                                    | The character's maximum hit points.                                                                                                                                                                                                                                                                                                        |
| `movementModes`         | [`MovementMode[]`](#movementmode)                           | An array of movement modes and their associated speeds.                                                                                                                                                                                                                                                                                    |
| `name`                  | `string`                                                    | The character's name.                                                                                                                                                                                                                                                                                                                      |
| `platinum`              | `number`                                                    | The number of platinum coins carried by the character.                                                                                                                                                                                                                                                                                     |
| `proficiencies`         | [`Proficiency[]`](#proficiency)                             | An array of skills, languages, saving throws, etc. that the character is proficient in.                                                                                                                                                                                                                                                    |
| `proficiencyBonus`      | `number`                                                    | The character's proficiency bonus (5e).                                                                                                                                                                                                                                                                                                    |
| `race`                  | `string`                                                    | The character's race, lineage, folk, etc.                                                                                                                                                                                                                                                                                                  |
| `senses`                | [`Sense[]`](#sense)                                         | A non-player character's senses.                                                                                                                                                                                                                                                                                                           |
| `silver`                | `number`                                                    | The number of copper coins carried by the character.                                                                                                                                                                                                                                                                                       |
| `skills`                | [`Skill[]`](#skill)                                         | The character's skills.                                                                                                                                                                                                                                                                                                                    |
| `skin`                  | `string`                                                    | The color of the character's skin.                                                                                                                                                                                                                                                                                                         |
| `size`                  | `string`                                                    | The character's size.                                                                                                                                                                                                                                                                                                                      |
| `speed`                 | `number`                                                    | The player character's movement speed per turn.                                                                                                                                                                                                                                                                                            |
| `spells`                | [`Spell[]`](#spell)                                         | An array of [spells](#spell) that this character can cast. This can be either a fully-formed [Spell](#spell) object or an object containing just the name of an SRD spell. **If a name is provided, the spell will be looked up in our database of SRD spells and used regardless of what values are provided in the rest of the inputs.** |
| `spellcastingAbility`   | `string`                                                    | The character's spellcasting ability name (abbreviated as int, e.g.).                                                                                                                                                                                                                                                                      |
| `spellFilters`          | `string[]`                                                  | An array of filters to be applied to the character's spellbook whenever it is displayed. These will be overwritten anytime the spellbook is filtered.                                                                                                                                                                                      |
| `spellSlots`            | [`SpellSlot[]`](#spellslot)                                 | Information about the spell slots for this character.                                                                                                                                                                                                                                                                                      |
| `systemKey`             | `string`                                                    | The key for the game system that the character is built for (e.g. '5e').                                                                                                                                                                                                                                                                   |
| `textBlocks`            | [`TextBlockSection[]`](#textblocksection)                   | General purpose text about the character broken into sections of title and body text blocks. Things like class features, racial features, and background features are found here.                                                                                                                                                          |
| `trackers`              | [`Tracker[]`](#tracker)                                     | An array of trackers for the character.                                                                                                                                                                                                                                                                                                    |
| `type`                  | `string`                                                    | The non-player character's type (e.g. Humanoid, Giant, etc.).                                                                                                                                                                                                                                                                              |
| `typeTags`              | `string[]`                                                  | An array of type tags (or subtypes) applicable to the non-player character (e.g. goblinoid).                                                                                                                                                                                                                                               |
| `weight`                | `string`                                                    | The character's weight.                                                                                                                                                                                                                                                                                                                    |

## CharacterDamageAdjustment

```json
{
  "condition": "Nonmagical",
  "damageType": "Bludgeoning"
}
```

| Attribute    | Type     | Description                                                                                                                          |
| ------------ | -------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `condition`  | `string` | The condition associated with the damage adjustment (e.g. silvered, magical, etc.). This is only displayed, not a mechanical effect. |
| `damageType` | `string` | The name of the damage type to adjust (e.g. Slashing, Piercing, etc.).                                                               |

## Class

```json
{
  "class": "Wizard",
  "level": 20
}
```

| Attribute | Type     | Description                                                 |
| --------- | -------- | ----------------------------------------------------------- |
| `class`   | `string` | The name of the character class.                            |
| `level`   | `number` | The number of levels the character has earned in the class. |

## MovementMode

```json
{
  "distance": 40,
  "mode": "Walking"
}
```

```json
{
  "distance": 80,
  "mode": "Fly"
}
```

| Attribute  | Type     | Description                                                    |
| ---------- | -------- | -------------------------------------------------------------- |
| `distance` | `number` | The distance the character can move in this mode.              |
| `mode`     | `string` | The name of the movement mode (e.g. `Walking`, `Fly`, `Swim`). |

## Proficiency

```json
{
  "name": "Dexterity",
  "type": "save"
}
```

| Attribute | Type     | Description                                                                                                                        |
| --------- | -------- | ---------------------------------------------------------------------------------------------------------------------------------- |
| `name`    | `string` | The name of the proficiency.                                                                                                       |
| `type`    | `string` | The type of proficiency. This is very flexible, but 5e has a few specific ones: `language`, `save`, `weapon`, `tool`, and `armor`. |

## SavingThrow

```json
{
  "abilityName": "wis",
  "difficultyClass": 16
}
```

| Attribute         | Type     | Description                                                 |
| ----------------- | -------- | ----------------------------------------------------------- |
| `abilityName`     | `string` | The name of the ability that this saving throw is based on. |
| `difficultyClass` | `number` | The difficulty class for this saving throw.                 |

## Sense

```json
{
  "distance": 120,
  "name": "Darkvision"
}
```

| Attribute  | Type     | Description                                                    |
| ---------- | -------- | -------------------------------------------------------------- |
| `distance` | `number` | The maximum distance at which the sense can be used.           |
| `name`     | `string` | The name of the sense (e.g. `Darkvision`, `Blindsight`, etc.). |

## Skill

```json
{
  "abilityName": "wis",
  "name": "Perception",
  "proficient": false
}
```

```json
{
  "abilityName": "dex",
  "bonus": 3,
  "doubleProficiency": true,
  "name": "Stealth",
  "proficient": true
}
```

| Attribute           | Type      | Description                                                                                    |
| ------------------- | --------- | ---------------------------------------------------------------------------------------------- |
| `abilityName`       | `string`  | The name of the ability that this skill is based on. For 5e, use the abbreviated ability name. |
| `bonus`             | `number`  | A bonus to add to the skill roll.                                                              |
| `doubleProficiency` | `boolean` | Whether or not the character has double proficiency (a.k.a. expertise) in this skill.          |
| `name`              | `string`  | The name of the skill (e.g. `Perception`, `Stealth`, etc.).                                    |
| `proficient`        | `boolean` | Whether or not the character is proficient in this skill.                                      |

## Spell

```json
{
  "canCastAtHigherLevel": true,
  "castingTime": "1 Action",
  "components": ["V", "S"],
  "damage": [
    {
      "bonus": 1,
      "dice": "1d4",
      "type": "Force"
    },
    {
      "bonus": 1,
      "dice": "1d4",
      "type": "Force"
    },
    {
      "bonus": 1,
      "dice": "1d4",
      "type": "Force"
    }
  ],
  "description": "You create three glowing darts of magical force. Each dart hits a creature of your choice that you can see within range. A dart deals 1d4 + 1 force damage to its target. The darts all strike simultaneously, and you can direct them to hit one creature or several.\n\nAt Higher Levels. When you cast this spell using a spell slot of 2nd level or higher, the spell creates one more dart for each slot level above 1st.",
  "duration": "Instantaneous",
  "higherLevelDescription": "When you cast this spell using a spell slot of 2nd level or higher, the spell creates one more dart for each slot level above 1st.",
  "higherLevels": [
    {
      "applyAtLevels": [2],
      "damage": {
        "bonus": 1,
        "dice": "1d4",
        "type": "Force"
      },
      "type": "per-slot"
    }
  ],
  "level": 1,
  "name": "Magic Missile",
  "range": "120 ft.",
  "rollsAttack": false,
  "savingThrow": {},
  "school": "Evocation",
  "tags": ["Sorcerer", "Wizard"]
}
```

When importing a character with spells, if the name of the spell matches a spell in the SRD, the SRD data will be used. Otherwise, the spell will be imported as a custom spell.

| Attribute                | Type                                      | Description                                                                                                                                                                                            |
| ------------------------ | ----------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `canBeCastAsRitual`      | `boolean`                                 | Whether or not the spell can be cast as a ritual.                                                                                                                                                      |
| `canCastAtHigherLevel`   | `boolean`                                 | Whether or not the spell can be cast at higher levels.                                                                                                                                                 |
| `castingTime`            | `string`                                  | The casting time for the spell (e.g. 1 Action, 10 minutes, etc.).                                                                                                                                      |
| `components`             | `string[]`                                | An array of the components required to cast the spell. For 5e, the options are `V`, `S`, and `M` for verbal, somatic, and material, respectively                                                       |
| `damage`                 | [`ActionStepDamage[]`](#actionstepdamage) | An array of damage dice rolls.                                                                                                                                                                         |
| `description`            | `string`                                  | The description of the spell.                                                                                                                                                                          |
| `duration`               | `string`                                  | The duration of the spell (e.g. Instantaneous, 1 minute, etc.).                                                                                                                                        |
| `higherLevelDescription` | `string`                                  | The description of how the spell changes when cast at higher levels.                                                                                                                                   |
| `higherLevels`           | [`SpellHigherLevel[]`](#spellhigherlevel) | An array of higher level spell effects.                                                                                                                                                                |
| `level`                  | `number`                                  | The level of the spell.                                                                                                                                                                                |
| `materials`              | `string`                                  | The material components required to cast the spell.                                                                                                                                                    |
| `name`                   | `string`                                  | The name of the spell.                                                                                                                                                                                 |
| `range`                  | `string`                                  | The range of the spell.                                                                                                                                                                                |
| `requiresConcentration`  | `boolean`                                 | Whether or not the spell requires concentration to maintain effects.                                                                                                                                   |
| `rollsAttack`            | `boolean`                                 | Whether or not the spell rolls an attack.                                                                                                                                                              |
| `savingThrow`            | [`SavingThrow`](#savingthrow)             | The saving throw associated with the spell.                                                                                                                                                            |
| `school`                 | `string`                                  | The school of magic the spell belongs to.                                                                                                                                                              |
| `tags`                   | `string[]`                                | An array of tags associated with the spell. These can be custom or describe common spell metadata such as `Damage` to indicate that it deals damage or `Wizard` to indicate that it is a Wizard spell. |

## SpellHigherLevel

```json
{
  "applyAtLevels": [2],
  "damage": {
    "bonus": 1,
    "dice": "1d4",
    "type": "Force"
  },
  "type": "per-slot"
}
```

| Attribute       | Type                                      | Description                                         |
| --------------- | ----------------------------------------- | --------------------------------------------------- |
| `applyAtLevels` | `number[]`                                | An array of levels at which this effect is applied. |
| `damage`        | [`ActionStepDamage[]`](#actionstepdamage) | An array of damage dice rolls.                      |
| `type`          | `string`                                  | The type of effect (e.g. `per-slot`, `per-level`).  |

## SpellSlot

```json
{
  "max": 4,
  "remaining": 4
}
```

Describes the max and remaining spell slots for a given level based on its position within an array.

| Attribute   | Type     | Description                                  |
| ----------- | -------- | -------------------------------------------- |
| `max`       | `number` | The maximum number of spell slots available. |
| `remaining` | `number` | The number of spell slots remaining.         |

## TextBlock

```json
{
  "body": "The dragon can breathe air and water.",
  "title": "Amphibious"
}
```

| Attribute | Type     | Description                  |
| --------- | -------- | ---------------------------- |
| `body`    | `string` | The body of the text block.  |
| `title`   | `string` | The title of the text block. |

## TextBlockSection

```json
{
  "title": "Abilities",
  "textBlocks": [
    {
      "body": "The dragon can breathe air and water.",
      "title": "Amphibious"
    },
    {
      "body": "If the dragon fails a saving throw, it can choose to succeed instead.",
      "title": "Legendary Resistance (3/Day)"
    },
    {
      "body": "The dragon can use its Frightful Presence. It then makes three attacks: one with its bite and two with its claws.",
      "title": "Multiattack"
    },
    {
      "body": "The dragon can take 3 legendary actions, choosing from the options below. Only one legendary action can be used at a time and only at the end of another creature's turn. The dragon regains spent legendary actions at the start of its turn.\n\nDetect. The dragon makes a Wisdom (Perception) check.\n\nTail Attack. The dragon makes a tail attack.\n\nWing Attack (Costs 2 Actions). The dragon beats its wings. Each creature within 10 feet of the dragon must succeed on a DC 19 Dexterity saving throw or take 13 (2d6 + 6) bludgeoning damage and be knocked prone. The dragon can then fly up to half its flying speed.",
      "title": "Legendary Actions"
    },
    {
      "body": "On initiative count 20 (losing initiative ties), the dragon takes a lair action to cause one of the following effects; the dragon can't use the same effect two rounds in a row:\n\n* Grasping roots and vines erupt in a 20-foot radius centered on a point on the ground that the dragon can see within 120 feet of it. That area becomes difficult terrain, and each creature there must succeed on a DC 15 Strength saving throw or be restrained by the roots and vines. A creature can be freed if it or another creature takes an action to make a DC 15 Strength check and succeeds. The roots and vines wilt away when the dragon uses this lair action again or when the dragon dies.\n\n* A wall of tangled brush bristling with thorns springs into existence on a solid surface within 120 feet of the dragon. The wall is up to 60 feet long, 10 feet high, and 5 feet thick, and it blocks line of sight. When the wall appears, each creature in its area must make a DC 15 Dexterity saving throw. A creature that fails the save takes 18 (4d8) piercing damage and is pushed 5 feet out of the wall's space, appearing on whichever side of the wall it wants. A creature can move through the wall, albeit slowly and painfully. For every 1 foot a creature travels through the wall, it must spend 4 feet of movement. Furthermore, a creature in the wall's space must make a DC 15 Dexterity saving throw once each round it's in contact with the wall, taking 18 (4d8) piercing damage on a failed save, or half as much damage on a successful one. Each 10-foot section of wall has AC 5, 15 hit points, vulnerability to fire damage, resistance to bludgeoning and piercing damage, and immunity to psychic damage. The wall sinks back into the ground when the dragon uses this lair action again or when the dragon dies.\n\n* Magical fog billows around one creature the dragon can see within 120 feet of it. The creature must succeed on a DC 15 Wisdom saving throw or be charmed by the dragon until initiative count 20 on the next round.",
      "title": "Lair Actions"
    },
    {
      "body": "At your discretion, a legendary (adult or ancient) green dragon can use one or both of the following additional lair actions while in its lair:\n\nCreeper Vines. The dragon can use the vines and roots within its lair to animate up to three Humanoid corpses, which become zombies. The zombies take their turn immediately after this lair action. Each one reverts to an inanimate corpse after 1 minute, when the dragon uses this lair action again, or when the zombie is destroyed.\n\nLashing Root. One large root or branch that is part of the lair makes a melee attack roll against a creature within 10 feet of it. It has a +7 bonus to hit and deals 10 (3d6) bludgeoning damage on a hit. If the target is a Medium or smaller creature, it must succeed on a DC 15 Strength saving throw or be knocked prone.",
      "title": "Additional Lair Actions"
    },
    {
      "body": "The region containing a legendary green dragon's lair is warped by the dragon's magic, which creates one or more of the following effects:\n\n* Thickets form labyrinthine passages within 1 mile of the dragon's lair. The thickets act as 10-foot-high, 10-foot-thick walls that block line of sight. Creatures can move through the thickets, with every 1 foot a creature moves costing it 4 feet of movement. A creature in the thickets must make a DC 15 Dexterity saving throw once each round it's in contact with the 'thickets or take 3 (1d6) piercing damage from thorns.\n\n* Each 10-foot-cube of thickets has AC 5, 30 hit points, resistance to bludgeoning and piercing damage, vulnerability to fire damage, and immunity to psychic and thunder damage.\n\n* Within 1 mile of its lair, the dragon leaves no physical evidence of its passage unless it wishes to. Tracking it there is impossible except by magical means. In addition, it ignores movement impediments and damage from plants in this area that are neither magical nor creatures, including the thickets described above. The plants remove themselves from the dragon's path.\nRodents and birds within 1 mile of the dragon's lair serve as the dragon's eyes and ears. Deer and other large game are strangely absent, hinting at the presence of an unnaturally hungry predator.\n\nIf the dragon dies, the rodents and birds lose their supernatural link to it. The thickets remain, but within 1d10 days, they become mundane plants and normal difficult terrain, losing their thorns.",
      "title": "Regional Effects"
    },
    {
      "body": "Either or both of these effects might appear in the area around a green dragon's lair, in addition to or instead of those described in the Monster Manual:\n\nInviting Whispers. Whispers rustle in the foliage within 1 mile of the dragon's lair. The words are indistinct, but a creature with an Intelligence score of 5 or higher interprets them as an invitation to move deeper into the greenery.\n\nTwisted Messengers. The dragon can cause any Tiny Beast within 1 mile of its lair to act as its mouthpiece. The effect is horrendous, as the creature's throat and mouth temporarily warp into a twisted version of the dragon's own in order to allow the dragon's voice to issue forth.",
      "title": "Additional Regional Effects"
    },
    {
      "body": "You can customize any dragon's stat block to reflect the dragon's unique character. Minor changes such as those below are easy to make and have no impact on a dragon's challenge rating.\n\nLanguages. Most dragons prefer to speak Draconic but learn Common for dealing with allies and minions. But given their high Intelligence and long life span, dragons can easily learn additional languages. You can add languages to a dragon's stat block.\n\nSkills. Most dragons are proficient in the Perception and Stealth skills, and many dragons have additional skill proficiencies. As with languages, you can customize a dragon's skill list (even doubling their proficiency bonus with certain skills) to reflect particular interests and activities. You can also give a dragon tool proficiencies, particularly if the dragon spends time in Humanoid form.\n\nSpells. See the \"Variant: Dragons as Innate Spellcasters\" inset(s), below.\n\nOther Traits and Actions. You can borrow traits and actions from other monsters to add unique flavor to a dragon. Consider these examples:\n\nFlyby, The dragon is an agile flier, quick to fly out of enemies' reach.\nThe dragon doesn't provoke an opportunity attack when it flies out of an enemy's reach.\n\nMimicry. Impersonating characters or their allies could be a fun trick for a crafty dragon.\nThe dragon can mimic any sounds it has heard, including voices. A creature that hears the sounds can tell they are imitations with a successful DC 16 Wisdom (Insight) check.\n\nRejuvenation. You might decide that dragons in your campaign, being an essential part of the Material Plane, are nearly impossible to destroy. A dragon's life essence might be preserved in the egg from which it first emerged, in its hoard, or in a cavernous hall at the center of the world, just as a lich's essence is hidden in a phylactery.\nIf it has an essence-preserving object, a destroyed dragon gains a new body in 1d10 days, regaining all its hit points and becoming active again. The new body appears within 5 feet of the object.\n\nSpecial Senses. Most dragons have blindsight and darkvision. You might upgrade blindsight to truesight, or you could give a dragon with a burrowing speed tremorsense.",
      "title": "Customizing Dragons"
    },
    {
      "body": "This dragon can innately cast three spells, once per day each, requiring no material components. Each spell's level can be no higher than 5th. The dragon's spell save DC is DC 16, and it has +8 to hit with spell attacks.\n   A suggested spell list is shown below, but you can also choose spells to reflect the dragon's character. A dragon who innately casts druid spells feels different from one who casts warlock spells. You can also give a dragon spells of a higher level than this rule allows, but such a tweak might increase the dragon's challenge rating—especially if those spells deal damage or impose conditions on targets.\n\n* invisibility\n\n* plant growth\n\n* speak with animals",
      "title": "Variant: Dragons as Innate Spellcasters"
    },
    {
      "body": "Dragons are innately magical creatures that can master a few spells as they age, using this variant.\n   A young or older dragon can innately cast a number of spells equal to its Charisma modifier. Each spell can be cast once per day, requiring no material components, and the spell's level can be no higher than one-third the dragon's challenge rating (rounded down). The dragon's bonus to hit with spell attacks is equal to its proficiency bonus + its Charisma bonus. The dragon's spell save DC equals 8 + its proficiency bonus + its Charisma modifier.\n   This dragon can innately cast three spells, once per day each, requiring no material components. Each spell's level can be no higher than 5th. The dragon's spell save DC is DC 16, and it has +8 to hit with spell attacks. See the spell page for a list of spells the dragon is capable of casting. A selection of examples are shown below:\n\n *cloudkill\n\n* charm monster\n\n* modify memory\n\n* mislead\n\n* hallucinatory terrain\n\n* dimension door",
      "title": "Variant: Dragons as Innate Spellcasters"
    }
  ]
}
```

| Attribute    | Type                        | Description                                    |
| ------------ | --------------------------- | ---------------------------------------------- |
| `textBlocks` | [`TextBlock[]`](#textblock) | An array of [`TextBlock`](#textblock) objects. |
| `title`      | `string`                    | The title of the section.                      |

## Tracker

```json
{
  "color": "Green",
  "max": 20,
  "name": "HP",
  "type": "Bar",
  "value": 20
}
```

| Attribute | Type     | Description                                                                                                          |
| --------- | -------- | -------------------------------------------------------------------------------------------------------------------- |
| `color`   | `string` | The color of the tracker bar. Valid options are `'Blue'`, `'Green'`, `'Orange'`, `'Purple'`, `'Red'`, and `'Yellow'` |
| `max`     | `number` | The maximum value for the tracker.                                                                                   |
| `name`    | `string` | The name displayed on the tracker.                                                                                   |
| `type`    | `string` | The type of tracker (`'Bar'` or `'Pip'`).                                                                            |
| `value`   | `number` | The tracker's current value.                                                                                         |
