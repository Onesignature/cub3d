# Cub3D

A 42 project: a basic 3D game engine built with **raycasting**, inspired by *Wolfenstein 3D*. The renderer projects a 3D view from a 2D map and supports textured walls, player movement, and collision.

> If you're learning raycasting for this project, **read the [Pikuma raycasting course](https://pikuma.com/courses/raycasting-engine-tutorial-algorithm-javascript) first** — understand it instead of copy-pasting Lodev code.

## Features

- Raycasting-based wall rendering with per-side textures
- Smooth player movement: walk, strafe, rotate
- Wall collision detection
- `.cub` map parser with texture, color, and player-spawn directives
- Built on **MiniLibX**

## Build

```bash
make
```

Produces the `cub3D` executable.

## Run

```bash
./cub3D maps/example.cub
```

## Controls

| Key | Action |
|---|---|
| `W` / `S` | Move forward / backward |
| `A` / `D` | Strafe left / right |
| `←` / `→` | Rotate view |
| `ESC` | Quit |

## Map format

A `.cub` file declares textures, floor/ceiling colors, and a tile grid. Tiles:

- `1` — wall
- `0` — empty space
- `N` / `S` / `E` / `W` — player start position + facing direction

Example:

```
111111
100001
1000N1
100001
111111
```

## Layout

- `main.c`, `cub3d.h` — entry + headers
- `parsing/` — `.cub` file parser and map validator
- `raycasting/` — DDA raycaster + texture sampling
- `key_handles/` — keyboard input
- `game_textures/` — wall textures
- `includes/`, `libft/`, `mlx/` — shared headers, libft, MiniLibX
- `maps/` — sample maps

## Resources

- [42 Cub3D subject](https://cdn.intra.42.fr/pdf/pdf/122814/en.subject.pdf)
- [Pikuma raycasting course](https://pikuma.com/courses/raycasting-engine-tutorial-algorithm-javascript)
