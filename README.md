# [![Bevy](assets/branding/bevy_ecss.png)](https://bevyengine.org)
[![MIT/Apache 2.0](https://img.shields.io/badge/license-MIT%2FApache-blue.svg)](https://github.com/afonsolage/bevy_ecss#license)
[![Realease Doc](https://docs.rs/bevy_ecss/badge.svg)](https://docs.rs/bevy_ecss)
[![Rust](https://github.com/afonsolage/bevy_ecss/workflows/CI/badge.svg)](https://github.com/afonsolage/bevy_ecss/actions)
[![Crate](https://img.shields.io/crates/v/bevy_ecss.svg)](https://crates.io/crates/bevy_ecss)
[![Bevy tracking](https://img.shields.io/badge/Bevy%20tracking-released%20version-lightblue)](https://github.com/bevyengine/bevy/blob/main/docs/plugins_guidelines.md#main-branch-tracking)

# Bevy ECSS

## What is Bevy ECSS?

Bevy ECSS is a crate which allows the usage of a subset of [`CSS`](https://developer.mozilla.org/en-US/docs/Web/CSS) to interact with [`bevy_ecs`](https://crates.io/crates/bevy_ecs). It's mainly aimed to apply styling on [`bevy_ui`](https://crates.io/crates/bevy) but it can be used by any component by implementing custom properties.

### Why the name?

Just because Bevy ECS + CSS is a perfect fit!

### Docs site

Reference guide, examples and more available here:
[docs](https://afonsolage.github.io/bevy_ecss/)

## Usage

To use Bevy ECSS just add a `StyleSheet` with a loaded `css` file to any entity and all style sheet rules will be applied to the entity and _all_ its [`descendants`](https://stackoverflow.com/questions/1182189/css-child-vs-descendant-selectors) (children of children of children and so on).

```rust
use bevy::prelude::*;
use bevy_ecss::prelude::*;

fn setup_awesome_ui(root: Entity, mut commands: Commands, asset_server: Res<AssetServer>) {
    commands
        .entity(root)
        .insert(StyleSheet::new(asset_server.load("sheets/awesome.css")));
}
```

That's it, now your UI will indeed look _awesome_!

## Bevy support table
| bevy  | bevy_ecss |
| :---: | :-------: |
|  0.8  |    0.1    |
|  0.9  |    0.2    |
|  0.10 |    0.3    |
|  0.11 |    0.4    |
|  0.12 |    0.5    |
|  0.12 |    0.6    |
|  0.13 |    0.7    |

## Contributing

Got some idea, feedback, question or found any bug? Feel free to open an issue at any time!

## License

Bevy ECSS is dual-licensed under either:

* MIT License ([LICENSE-MIT](LICENSE-MIT) or [http://opensource.org/licenses/MIT](http://opensource.org/licenses/MIT))
* Apache License, Version 2.0 ([LICENSE-APACHE](LICENSE-APACHE) or [http://www.apache.org/licenses/LICENSE-2.0](http://www.apache.org/licenses/LICENSE-2.0))

This means you can select the license you prefer!
This dual-licensing approach is the de-facto standard in the Rust ecosystem and there are [very good reasons](https://github.com/bevyengine/bevy/issues/2373) to include both.
