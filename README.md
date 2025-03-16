# unreal-gameplay-ability-system-gas
Implementation of GAS from scratch. Also has some UI, movement, animations etc. Most important parts ripped from Azure cloud. Ask for a full demo if interested. Original readme below.

========================================

Introduction
This GAS Demo shows Gameplay Ability System in work.

Demo has 1 skill, UI, movement system. The skill (W) regenerates health and gives movement speed, takes mana, has cooldown.

The components are

Character Controller: BP_Player (GasCharacter)
C++ Scripts: GasCharacter, DemoCharacterAttributeSet, DemoGameplayAbility, Enum DemoAbilityInputID, GasDemoAbilitySystemComponent
UI: WPB_CharacterUI (Shows skills, cooldown, mana, health)
GameMode: GM_Demo
Map: DemoLevel (run this)
Input: IMC_DemoHero -> IA_Heal (W) Ready Gameplay Ability System assets in Content/Blueprints/Abilities
Gameplay Abilities: GA_Heal
Gameplay Effects: GE_Heal_Cost, GE_Regenerate, GE_AddSpeedForDuration, GE_CharacterBaseHealthManaRegen (moba health & mana regen), GE_CharacterDefaults (default attribute values)
Gameplay Cues: GC_Abilities_RegenHaste
Gameplay Event Tags: Spell.Heal
Gameplay Cue Tags: Abilities.RegenHaste
Getting Started
The repository has been uploaded with Unreal specific .gitignore file and requires one to build the project with .uproject file before opening it.

For the demo, open DemoLevel map.

Controls: Right mouse button moves the character. W uses the skill (or pressing the second UI button).

For debugging GAS enter console command showdebug abilitysystem

Networking
Playing the DemoLevel from editor for 2 players using Net Mode Play As Listen Server shows that the movement and use of the W skill GA is replicated by showing movement and GC on second screen.

AttributeSet replicates attributes and has OnReplication methods.

The demo uses default networking in blueprint level and the networking for the GAS setup is defined in C++ level in the scripts that make up the GAS base.

Future updates
There's still some tasks/things left to look at. For example debugging the networked state for multiple players, giving UI to all players, controlling the other characters. Being new to Unreal means there's many open questions but with time, study and work everything becomes clear.
