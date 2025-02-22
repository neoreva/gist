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

```rs
#[derive(Debug, Clone, Serialize, Deserialize, PartialEq)]
#[serde(deny_unknown_fields, rename_all = "snake_case")]
pub enum DealsDamage {
    /// Received damage is applied to the entity.
    Yes,
    /// Received damage is not applied to the entity.
    No,
    /// Received damage is not applied to the entity, but the side effects of the attack are.
    /// This means that the attacker's weapon loses durability, enchantment side effects are applied,
    /// and so on.received damage is not applied to the entity, but the side effects of the attack are.
    /// This means that the attacker's weapon loses durability, enchantment side effects are applied, and so on.
    NoButSideEffectsApply,
    /// If true, the damage dealt to the entity will remove health,
    /// if false the entity will ignore the damage.
    #[serde(untagged)]
    Bool(bool),
}
```

This is how we documented this field in Spadix.

### [minecraft:genetics](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/entitycomponents/minecraftcomponent_genetics?view=minecraft-bedrock-stable)

The field `use_simplified_breeding` is missing a description.

```rs
/// When set to 'true', this optional flag prohibits the inheritance of hidden parent alleles as main alleles in children and the inheritance of main alleles as hidden alleles in children. This allows for easier implementation of basic breeding logic.
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

This component is incorrect compared to the example provided.

```rs
#[spadix_macros::default]
#[derive(Debug, Clone, Serialize, Deserialize)]
#[serde(deny_unknown_fields)]
#[namespace = "minecraft:raid_trigger"]
/// Attempts to trigger a raid at the entity's location.
pub struct RaidTrigger {
    /// Event to run when a raid is triggered.
    triggered_event: EventDescriptor,
}
```

This is how we documented it inside of Spadix.

### [minecraft:behavior.follow_target_captain]

Missing `speed_multiplier` is missing a description and a default.

```rs
/// Movement speed multiplier of the mob when using this AI Goal.
#[default(1.0)]
speed_multiplier: f32,
```

This is how we documented it in Spadix. These were based on other defaults in the AddOn format.

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

### [minecraft:has_ranged_weapon]()

This is self evident:

- `dandelion not require any parameters to work properly. It can be used as a standalone filter.`

> This one made me laugh if anything

### [minecraft:item](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/itemreference/examples/itemcomponents/minecraft_item?view=minecraft-bedrock-stable)

This is listed under the components.
When this should be listed under the item reference root, rather than the components list.

### [filters](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/filterlist?view=minecraft-bedrock-stable) (Any filter in the filters section)

The `At Full..:` and the `At Short (using Defaults)..:` sections have issues:

- Formatted weirdly with how the `..` is followed by the `:`.
- The `value` fields value is always surrounded by `"` even if the value for `value` is not a string.
  - [in_caravan](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/filters/in_caravan?view=minecraft-bedrock-stable)
  - [inactivity_timer](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/filters/inactivity_timer?view=minecraft-bedrock-stable)
  - This happens with all of the filters that have non string values.
- In the filter sidebar, `in_caravan` is listed above `in_block`, which is not the correct order alphabetically.
- Subject is capitalized in the description when it should be lowercase in the following filters:
  - [is_biome](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/filters/is_biome?view=minecraft-bedrock-stable)
  - [is_in_village](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/filters/is_in_village?view=minecraft-bedrock-stable)
  - [is_sleeping](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/filters/is_sleeping?view=minecraft-bedrock-stable)
  - [is_snow_covered](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/filters/is_snow_covered?view=minecraft-bedrock-stable)
- The following filters are not listed in the filter sidebar, but they can be found on the filter list page.
  - `is_navigating`
  - `has_property`
  - `float_property`
  - `bool_property`
  - `enum_property`
  - `home_distance`
  - `int_property`
  - `is_baby`
  - `is_bound_to_creaking_heart`
  - `is_missing_health`
  - `is_navigating`
  - `is_waterlogged`
  - `owner_distance`

### [in_caravan](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/filters/in_caravan?view=minecraft-bedrock-stable)

This filter has elements of `minecraft:damage_sensor` strewn about within the documentation. This does not seem correct.

### [weather](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/filters/weather?view=minecraft-bedrock-stable) / [weather_at_position](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/filters/weather_at_position?view=minecraft-bedrock-stable)

These seem like they were quickly documented based on the filter `is_family`. The descriptions are incorrect for the `value` field on both of these filters. The valid values for this field are also undocumented.

````rs

```rs
#[spadix_macros::default]
#[derive(Debug, Clone, Serialize, Deserialize)]
#[serde(rename_all = "lowercase")]
pub enum Weather {
    Precipitation,
    Thunderstorm,
    Clear,
}
````

> Note: Each of these variants are lowercase as stated above, this is how we work with the types within rust.
> This is what we have documented in Spadix, based on the bedrock-samples.

### [is_altitude](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/filters/is_altitude?view=minecraft-bedrock-stable)

The description is outdated as bedrock is no longer at y level 0.

### [light_level](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/filters/light_level?view=minecraft-bedrock-stable)

Is this type 0-15 and not 0-16, as there is no clarity if this range is inclusive or exclusive.
As the light level is from 0 to 15 in game, this description is quite unclear.

### Animation Controllers

- [This page is broken and not linked anywhere.](https://learn.microsoft.com/en-us/minecraft/creator/reference/content/animationsreference/examples/animationcontroller?view=minecraft-bedrock-stable)

The code below is in reference to this page: [Animation Documentation - Animation Controllers](https://learn.microsoft.com/en-us/minecraft/creator/documents/animations/animationcontroller?view=minecraft-bedrock-stable)

```rs
/// animation_controller -----------------------------

#[spadix_macros::default]
#[derive(Debug, Clone, Serialize, Deserialize)]
#[serde(deny_unknown_fields)]
pub struct AnimationControllersModule {
    format_version: SemVer,

    animation_controllers: HashMap<AnimationControllerIdentifier, AnimationController>,
}


#[spadix_macros::default]
#[derive(Debug, Clone, Serialize, Deserialize)]
#[serde(deny_unknown_fields)]
struct AnimationController {
    initial_state: Option<AnimationStateIdentifier>,
    /// The group of animations to process.
    /// May include variables to create more dynamic states.
    /// May include a transitions value to allow state blending between animations,
    /// such as querying the current state. Variables may be set by the game or user defined in a custom entity file.
    #[default]
    states: HashMap<AnimationStateIdentifier, State>,
}

#[spadix_macros::default]
#[derive(Debug, Clone, Serialize, Deserialize)]
#[serde(deny_unknown_fields)]
struct State {
    #[default]
    animations: Vec<StateAnimation>,

    #[default]
    transitions: Vec<HashMap<BasicIdentifier, Molang>>,

    blend_transition: Option<f32>,
    blend_via_shortest_path: Option<bool>,

    #[default]
    particle_effects: Vec<ParticleEffect>,

    #[default]
    sound_effects: Vec<SoundEffect>,

    #[default]
    on_entry: Vec<StateTrigger>,

    #[default]
    on_exit: Vec<StateTrigger>,
}

/// animations ------------------


#[spadix_macros::default]
#[derive(Debug, Clone, Serialize, Deserialize)]
#[serde(deny_unknown_fields)]
pub struct BoneAnimation {
    /// The set of key frames that might be specified during an animation to create greater granularity.
    rotation: Option<KeyFrames>,
    /// The position of a bone in space.
    position: Option<KeyFrames>,

    relative_to: Option<RelativeTo>,

    /// The scale of the bones.
    scale: Option<Either<Molang, KeyFrames>>,
}

#[spadix_macros::default]
#[derive(Debug, Clone, Serialize, Deserialize)]
#[serde(deny_unknown_fields)]
pub struct AnimationChannel {
    /// At what time does the system consider this animation finished?
    animation_length: Option<f32>,

    #[default(Molang::Expr("query.anim_time + query.delta_time".to_string()))]
    anim_time_update: Molang,

    #[default(Molang::Flt(1.0))]
    /// How much this animation is blended with the others. 0.0 = off. 1.0 = fully apply all transforms. Can be an expression
    // TODO: Percent Inclusive
    blend_weight: Molang,

    #[default]
    /// The bone in the geometry section and various settings. Omitting a channel skips that channel for this animation of this bone. Any of these values can be expressions or values.
    bones: HashMap<BoneIdentifier, BoneAnimation>,

    /// Should the animation loop back to t=0.0 when it finishes?
    #[serde(rename = "loop")]
    #[default(ValueOrBool::Boolean(false))]
    loop_animation: ValueOrBool<AnimationLoop>,

    #[default]
    sound_effects: Timeline<ValueOrMany<SoundEffect>>,

    #[default]
    timeline: Timeline<Molang>,

    #[default]
    particle_effects: Timeline<ValueOrMany<ParticleEffect>>,

    start_delay: Option<Molang>,

    /// Should the animation pose of the bone be set to the bind pose before applying this animation,
    /// thereby overriding any previous animations to this point?
    override_previous_animation: Option<bool>,
}
```

This is a crunched down version of what we have for the Spadix structures.

The table on this page is a complete mess, as it seems to be a combination of various types used in and around animations/animation_controllers.

Though this is a rough overview of the types, it should be enough to get across that [this](https://learn.microsoft.com/en-us/minecraft/creator/documents/animations/animationcontroller?view=minecraft-bedrock-stable#animation-controller-parameters) table is screwed up.

## Bedrock Samples

When parsing JSONUI we found that the samples repository has an miss-named file in the `./resource_pack/
ui` folder.

- [`persona_SDL.json`](https://github.com/Mojang/bedrock-samples/blob/preview/resource_pack/ui/persona_SDL.json) should really be `persona_sdl.json` so it lines up with [`_ui_defs.json:117`](https://github.com/Mojang/bedrock-samples/blob/b353e8cbe549f04dd63290b765715d0a4202af51/resource_pack/ui/_ui_defs.json#L117). This is not an issue in the base game definitions, this only shows up in the samples.

## A Note about Spadix

Though this may be the first time this name has ever been brought up.
We have all of the AddOn format JSON parsed and documented inside of our codebase.
Our intension is to provide documentation for things that are not documented.
