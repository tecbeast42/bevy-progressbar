# Bevy Progressbar

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Doc](https://docs.rs/bevy-progressbar/badge.svg)](https://docs.rs/bevy-progressbar)
[![Crate](https://img.shields.io/crates/v/bevy-progressbar.svg)](https://crates.io/crates/bevy-progressbar)
[![Build Status](https://github.com/tecbeast42/bevy-progressbar/actions/workflows/rust.yml/badge.svg)](https://github.com/tecbeast42/bevy-progressbar/actions/workflows/rust.yml)
[![Bevy tracking](https://img.shields.io/badge/Bevy%20tracking-v0.14-lightblue)](https://github.com/bevyengine/bevy/blob/main/docs/plugins_guidelines.md#main-branch-tracking)

Generate progressbars in bevy ui from simple values. 

![Preview](./example.gif)

## Features

- [x] multi section progressbars 
- [x] gpu based shader for rendering

## Install

```rust
cargo add bevy-progressbar
```

## Usage

> See examples for better understanding

```rust
fn setup(mut commands: Commands, mut materials: ResMut<Assets<ProgressBarMaterial>>) {
    let bar = ProgressBar::new(vec![(1000, Color::RED),(2000, Color::BLUE),(4000, Color::GREEN)]);
    let style = Style {
        position_type: PositionType::Absolute,
        width: Val::Px(400.0),
        height: Val::Px(200.0),
        top: Val::Px(400.0),
        ..bevy_utils::default()
    };
    commands.spawn(
        ProgressBarBundle::new(style, bar, &mut materials);
    );
}
```

| Version | Bevy Version |
|---------|--------------|
| 0.8.0   | 0.14         |
| 0.7.0   | 0.13         |
| 0.6.0   | 0.12         |
| 0.4.0   | 0.11         |
| 0.3.0   | 0.10         |
| 0.2.1   | 0.9          |

## TODO

- [x] optimize the image creation, by just doing one line and let the gpu use nearst neighbour to scale the texture
- [ ] (optional) render an outline of the progessbar 
- [ ] (optional) allow or rounded corners
