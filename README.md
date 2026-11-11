# Asteroids

A classic Asteroids-style arcade game in Python and pygame, built while working through the boot.dev back-end course.

**What it shows:** Python fundamentals · classes and a game loop · collision detection · Built without AI

## Why I built it
I wanted to practice Python by building something I could play, not just exercises. It was one of the larger projects in the boot.dev path, and I wrote the game code myself without AI help.

## What it does
- You fly a triangular ship in a 1280 x 720 window. Rotate with `A` and `D`, thrust forward and back with `W` and `S`, and fire with `Space` (shots have a 0.3 second cooldown).
- Asteroids spawn at random edges of the screen at a steady rate, in three sizes.
- Shooting an asteroid splits it into two smaller ones that fly off at different angles and a bit faster. The smallest size is destroyed outright.
- Touching an asteroid ends the game.
- A small logger writes game events (shots, splits, hits) to `game_events.jsonl` and a few seconds of periodic state snapshots to `game_state.jsonl`.

## Tech
- Python 3.13
- pygame 2.6.1
- Code layout: `main.py` (game loop and collisions), `circleshape.py` (base class with circle collision), `player.py`, `asteroid.py`, `asteroidfield.py` (spawning), `shot.py`, `constants.py`, `logger.py`

## Run it locally
```bash
pip install pygame==2.6.1
python main.py
```
The project also includes a `pyproject.toml` and `uv.lock`, so `uv run main.py` works if you use [uv](https://docs.astral.sh/uv/).

## Play it in the browser
A pygbag build with a few extras (screen wrap-around, restart after game over) lives in [Asteroids-web](https://github.com/jbouchey/Asteroids-web).

## What I learned
- Structuring a game with a sprite class hierarchy and sprite groups
- Frame-rate independent movement using delta time
- Circle-based collision detection and splitting objects on impact

---
Part of [bouchey.dev](https://bouchey.dev).
