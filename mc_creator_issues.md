---
author: The Neoreva Team
---

# Documentation/Sample Issues

## Issues in the Minecraft Creator Documentation

Throughout the past few months We have compiled a list of issues present on the Minecraft Creator Docs.

Rather than making a barrage of issues, we put together a list of every issue we encountered.

Notably, a large chunk of the issues that used to be on this list are now fixed as of the 2/21/25 content update.

### [minecraft:body_rotation_blocked](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/entitycomponents/minecraftcomponent_body_rotation_blocked?view=minecraft-bedrock-stable)

This component uses spaces to separate the name in the sidebar rather than `_`.

### [minecraft:breedable](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/entitycomponents/minecraftcomponent_breedable?view=minecraft-bedrock-stable)

The documentation fails to mention that:
`minecraft:breedable` requires the behavior `minecraft:behavior.breed` in order to breed.

### [minecraft:damage_sensor](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/entitycomponents/minecraftcomponent_damage_sensor?view=minecraft-bedrock-stable)

The field `deals_damage` under the `Triggers item type` table is typed a as a `boolean`, but the value can also be a string as stated in the description.
The following show up in different places across the samples repo:

- [`"no_but_side_effects"`](https://github.com/Mojang/bedrock-samples/blob/43ca2795c201b6fff53f38597c4d01f6c4593e1a/behavior_pack/entities/creaking.json#L135)
- [`"no"`](https://github.com/Mojang/bedrock-samples/blob/43ca2795c201b6fff53f38597c4d01f6c4593e1a/behavior_pack/entities/ender_dragon.json#L84)
- [`"yes"`](https://github.com/Mojang/bedrock-samples/blob/43ca2795c201b6fff53f38597c4d01f6c4593e1a/behavior_pack/entities/creaking.json#L127)
- [`true`](https://github.com/Mojang/bedrock-samples/blob/43ca2795c201b6fff53f38597c4d01f6c4593e1a/behavior_pack/entities/frog.json#L90)
- [`false`](https://github.com/Mojang/bedrock-samples/blob/43ca2795c201b6fff53f38597c4d01f6c4593e1a/behavior_pack/entities/allay.json#L84)

### [minecraft:genetics](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/entitycomponents/minecraftcomponent_genetics?view=minecraft-bedrock-stable)

The field `use_simplified_breeding` is missing a description.

```
When set to 'true', this optional flag prohibits the inheritance of hidden parent alleles as main alleles in children and the inheritance of main alleles as hidden alleles in children. This allows for easier implementation of basic breeding logic.
```

This is what we have in Spadix.

### [minecraft:knockback_resistance](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/entitycomponents/minecraftcomponent_knockback_resistance?view=minecraft-bedrock-stable)

The table given for this component is wrong, given that the type mentions the `max` field. This should be a field in the table, not mentioned in the type. The examples include the correct usage.

### [minecraft:lava_movement](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/entitycomponents/minecraftcomponent_lava_movement?view=minecraft-bedrock-stable)

The `Vanilla entities using` section uses `minecraft:lookat` and not `minecraft:lava_movement`

### [minecraft:projectile](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/entitycomponents/minecraftcomponent_projectile?view=minecraft-bedrock-stable#spawn_aoe_cloud-parameters)

The following fields on this component are screwed up:

- `stop_on_hurt` should be a `boolean` but it is listed as a `String`
- `on_hurt` has the wrong type entirely when compared to it's example value.

Also, all of the projectile sub-objects are missing after the update on 2/21/25

### [minecraft:raid_trigger](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/entitycomponents/minecraftcomponent_raid_trigger?view=minecraft-bedrock-stable)

This component is incorrect compared to the [samples](https://github.com/Mojang/bedrock-samples/blob/43ca2795c201b6fff53f38597c4d01f6c4593e1a/behavior_pack/entities/player.json#L36).

### [minecraft:behavior.follow_target_captain]

Missing `speed_multiplier` is missing a description and a default.

```rs
/// Movement speed multiplier of the mob when using this AI Goal.
#[default(1.0)]
speed_multiplier: f32,
```

This is how we documented it in Spadix.
These were based on other defaults in the AddOn format.

### [minecraft:behavior.go_and_give_items_to_noteblock](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/entitygoals/minecraftbehavior_go_and_give_items_to_noteblock?view=minecraft-bedrock-stable)

The default for `throw_sound` should be the same as the default for `throw_sound` as given in [`minecraft:behavior.go_and_give_items_to_noteblock`](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/entitygoals/minecraftbehavior_go_and_give_items_to_owner?view=minecraft-bedrock-stable)

### [minecraft:behavior.nap](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/entitygoals/minecraftbehavior_nap?view=minecraft-bedrock-stable)

Documentation is missing for the following fields:

- `can_nap_filters`
- `wake_mob_exceptions`

### [minecraft:behavior.random_fly](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/entitygoals/minecraftbehavior_random_fly?view=minecraft-bedrock-stable)

Documentation is missing for the following fields:

- `avoid_damage_blocks`
- `y_offset`

### [minecraft:behavior.stalk_and_pounce_on_target](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/entitygoals/minecraftbehavior_stalk_and_pounce_on_target?view=minecraft-bedrock-stable#stuck-blocks-item-type)

The field `stuck_blocks` is not typed correctly, it should be a `Minecraft Filter` object. This field is also missing a description.

### [minecraft:emitter_local_space](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/particlesreference/particlecomponents/minecraftemitter_local_space?view=minecraft-bedrock-stable)

The sentence "Rotation works the same way for rotation." does not make sense grammar wise.

### [minecraft:recipe_furnace](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/recipereference/examples/recipedefinitions/minecraftrecipe_furnace?view=minecraft-bedrock-stable)

This page has missing fields:

- `unlock`
- `priority`

As these fields can be found [here](https://github.com/search?q=repo%3AMojang%2Fbedrock-samples%20%22recipe_furnace%22%20unlock&type=code)

### [minecraft:recipe_shaped](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/recipereference/examples/recipedefinitions/minecraftrecipe_shaped?view=minecraft-bedrock-stable)

The following are issues on this page:

- The field `assume_symmetry` is listed twice.
- The `unlock` field is missing.
- The `key` field is a map of key value pairs, which is more descriptive than array.
- `group` and `unlock` are missing from the docs.
  - These can be found [here](https://github.com/search?q=repo%3AMojang%2Fbedrock-samples+%22recipe_shaped%22+group+unlock&type=code).
- Defaults are missing from most of these fields as well.

### [minecraft:recipe_smithing_transform](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/recipereference/examples/recipedefinitions/minecraftrecipe_smithingtransform?view=minecraft-bedrock-stable)

Incorrect grammar used for the `addition` description. `"minecraft:netherite_ingot."` is not a direct quote, rather it's a string, so the period should be outside of the quotation.
The same issue occurs in the description for `base` with `"result."`.

### [minecraft:world_age_filter](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/definitions/nestedtables/world_age_filter?view=minecraft-bedrock-stable)

This spawn rule component is missing the field `max`.

### [minecraft:has_ranged_weapon](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/filters/has_ranged_weapon?view=minecraft-bedrock-stable)

This is self evident:

- `dandelion not require any parameters to work properly. It can be used as a standalone filter.`

> This one made me laugh if anything

### [minecraft:item](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/itemreference/examples/itemcomponents/minecraft_item?view=minecraft-bedrock-stable)

This is listed under the components.
When this should be listed under the item reference root, rather than the components list.

### [Filters](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/filterlist?view=minecraft-bedrock-stable) (Any filter in the filters section)

The `At Full..:` and the `At Short (using Defaults)..:` sections have issues:

- Formatted weirdly with how the `..` is followed by the `:`.
- The `value` fields value is always surrounded by `"` even if the value for `value` is not a string.
  - [in_caravan](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/filters/in_caravan?view=minecraft-bedrock-stable)
  - [inactivity_timer](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/filters/inactivity_timer?view=minecraft-bedrock-stable)
  - This happens with all of the filters that have non string values.

### [Filters Sidebar](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/filterlist?view=minecraft-bedrock-stable) (Any filter in the filters section)

In the filter sidebar, the `in_caravan` filter is listed above `in_block`, which is not the correct order alphabetically.

### Subject grammar issue

Subject is capitalized in the description when it should be lowercase in the following filters:

- [is_biome](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/filters/is_biome?view=minecraft-bedrock-stable)
- [is_in_village](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/filters/is_in_village?view=minecraft-bedrock-stable)
- [is_sleeping](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/filters/is_sleeping?view=minecraft-bedrock-stable)
- [is_snow_covered](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/filters/is_snow_covered?view=minecraft-bedrock-stable)

### Missing filter sidebar entries

The following filters are not listed in the filter sidebar, but they can be found on the [filter list page](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/filterlist?view=minecraft-bedrock-stable).

- [`is_navigating`](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/filters/is_navigating?view=minecraft-bedrock-stable)
- [`has_property`](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/filters/has_property?view=minecraft-bedrock-stable)
- [`float_property`](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/filters/float_property?view=minecraft-bedrock-stable)
- [`bool_property`](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/filters/bool_property?view=minecraft-bedrock-stable)
- [`enum_property`](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/filters/enum_property?view=minecraft-bedrock-stable)
- [`int_property`](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/filters/int_property?view=minecraft-bedrock-stable)
- [`home_distance`](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/filters/home_distance?view=minecraft-bedrock-stable)
- [`is_baby`](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/filters/is_baby?view=minecraft-bedrock-stable)
- [`is_bound_to_creaking_heart`](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/filters/is_bound_to_creaking_heart?view=minecraft-bedrock-stable)
- [`is_missing_health`](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/filters/is_missing_health?view=minecraft-bedrock-stable)
- [`is_waterlogged`](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/filters/is_waterlogged?view=minecraft-bedrock-stable)
- [`owner_distance`](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/filters/owner_distance?view=minecraft-bedrock-stable)

### Filters missing in sidebar and [the filter list](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/filterlist?view=minecraft-bedrock-stable)

- [`in_overworld`](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/filters/in_overworld?view=minecraft-bedrock-stable)
- [`is_sitting`](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/filters/is_sitting?view=minecraft-bedrock-stable)
- [`taking_fire_damage`](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/filters/taking_fire_damage?view=minecraft-bedrock-stable)

These issues were discovered when we went to document the parsed information from bedrock samples.

### [in_caravan](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/filters/in_caravan?view=minecraft-bedrock-stable)

This filter has elements of `minecraft:damage_sensor` strewn about within the documentation. This does not seem correct.

### [weather](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/filters/weather?view=minecraft-bedrock-stable) / [weather_at_position](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/filters/weather_at_position?view=minecraft-bedrock-stable)

- These seem like they were quickly documented based on the filter `is_family`. The descriptions are incorrect for the `value` field on both of these filters. The valid values for this field are also undocumented.
- The `value` field for these filters are not documented:
  - [`precipitation`](https://github.com/Mojang/bedrock-samples/blob/43ca2795c201b6fff53f38597c4d01f6c4593e1a/behavior_pack/entities/bee.json#L370)
  - [`clear`](https://github.com/Mojang/bedrock-samples/blob/43ca2795c201b6fff53f38597c4d01f6c4593e1a/behavior_pack/entities/bee.json#L399)
  - [`thunderstorm`](https://github.com/Mojang/bedrock-samples/blob/43ca2795c201b6fff53f38597c4d01f6c4593e1a/behavior_pack/entities/fox.json#L299C1-L299C11)

### [is_altitude](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/filters/is_altitude?view=minecraft-bedrock-stable)

The description is outdated as bedrock is no longer at y level 0.

### [light_level](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/filters/light_level?view=minecraft-bedrock-stable)

Is this type 0-15 and not 0-16, as there is no clarity if this range is inclusive or exclusive.
As the light level is from 0 to 15 in game, this description is quite unclear.

### Animation Controllers

- [This page is broken and not linked anywhere.](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/animationsreference/examples/animationcontroller?view=minecraft-bedrock-stable)

- The table on [this](https://learn.microsoft.com/en-us/minecraft/creator/documents/animations/animationcontroller?view=minecraft-bedrock-stable#animation-controller-parameters) page is a complete mess, as it seems to be a combination of various types used in and around animations/animation_controllers
  - [`creaking.animation.json`](https://github.com/Mojang/bedrock-samples/blob/43ca2795c201b6fff53f38597c4d01f6c4593e1a/resource_pack/animations/creaking.animation.json)
  - [`creaking.animation.controller.json`](https://github.com/Mojang/bedrock-samples/blob/43ca2795c201b6fff53f38597c4d01f6c4593e1a/resource_pack/animation_controllers/creaking.animation_controllers.json)

## Bedrock Samples

### JSONUI

When parsing JSONUI we found that the samples repository has an miss-named file in the `./resource_pack/
ui` folder.

- [`persona_SDL.json`](https://github.com/Mojang/bedrock-samples/blob/preview/resource_pack/ui/persona_SDL.json) should really be `persona_sdl.json` so it lines up with [`_ui_defs.json:117`](https://github.com/Mojang/bedrock-samples/blob/b353e8cbe549f04dd63290b765715d0a4202af51/resource_pack/ui/_ui_defs.json#L117). This is not an issue in the base game definitions, this only shows up in the samples.

There are a good chunk of errors inside of the games JSONUI files, with different elements and parents that are undefined.
We do not have an exact list at this moment, but at some point a list will be made for this.

### [sounds.json](https://github.com/Mojang/bedrock-samples/blob/43ca2795c201b6fff53f38597c4d01f6c4593e1a/resource_pack/sounds.json#L7160)

Every `interactive_sound` entry includes an extra `"sounds"` field under the `"fall"` event.

This was discovered when we parsed the samples with Spadix during definition testing.

## Script API

### [MoonPhase](https://learn.microsoft.com/en-us/minecraft/creator/scriptapi/minecraft/server/moonphase?view=minecraft-bedrock-stable)

The comments for this section of the docs are not scientifically accurate.
As the documentation that mentions how the phases follow one another is wrong.

```rs
/// The fullness of the moon controls various mob behaviors such as the number of slimes
/// that spawn in Swamp biomes, the chance skeletons and zombies have to spawn with armor,
/// as well as the chance for spiders to spawn with certain status effects.
pub enum MoonPhase {
    /// The darkest moon phase.
    /// This phase follows the Waning Crescent.
    NewMoon = 4,

    /// The phase following the New Moon.
    WaxingCrecent = 5,

    /// The phase following the Waxing Crescent.
    FirstQuarter = 2,

    /// The phase following the First Quarter.
    WaxingGibbous = 7,

    /// The brightest moon phase.
    /// This phase follows the Waxing Gibbous.
    /// During this phase, cats have a 50% chance of spawning as black cats.
    FullMoon = 0,

    /// The phase following the Full Moon.
    WaningGibbous = 1,

    /// The phase following the Waning Gibbous.
    LastQuarter = 6,

    /// The phase following the Last Quarter.
    WaningCrecent = 3,
}
```

This is how we have it documented in Spadix, with corrected comments based off of this [Nasa Website](https://science.nasa.gov/moon/moon-phases/).

## A Note about Spadix

Though this may be the first time this name has ever been brought up.
We have all of the stable AddOn JSON format parsed and documented inside of the Spadix codebase.
Our intension is to provide documentation for things that are not documented.
Spadix is not just for documentation, rather it's something that is able to take advantage of the AddOn format programmatically.
