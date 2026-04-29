# timer_cli
`$ timer 1h30m`
```

             ███    █         █████  ███ 
            █   █  ██     █   █     █   █
            █   █   █         ████  ████ 
            █   █   █     █       █     █
             ███   ███        ████   ███ 

    [──────────────────────────────────────────]

                  ends 15:41  ·  0%
```

A full-screen countdown timer for the terminal. No dependencies.

## Install

Add the function to your shell config:

```bash
echo 'source ~/timer.sh' >> ~/.bashrc
source ~/.bashrc
```

## Usage

```bash
timer <duration> [options]
```

### Duration formats

| Input | Meaning |
|-------|---------|
| `25` | 25 minutes |
| `25m` | 25 minutes |
| `1h30m` | 1 hour 30 minutes |
| `15m30s` | 15 minutes 30 seconds |
| `90s` | 90 seconds |

### Options

| Flag | Description |
|------|-------------|
| `-m "msg"` | Show a label under the timer |
| `--no-bell` | Suppress terminal bell on finish |

### Examples

```bash
timer 25
timer 1h30m
timer 25m -m "Focus session"
timer 15m --no-bell
```

## Features

- Big centered digits — no figlet needed
- Color shifts green → yellow → red as time runs out
- Smooth 10 fps progress bar
- Alternate screen — terminal history is untouched
- Desktop notification on finish (if `notify-send` is available)
- Sound on finish (if `paplay` is available)

## Show hours and minutes only

In the timer function, change:

```bash
printf -v time_str "%02d:%02d:%02d" "$rh" "$rm" "$rs"
```

to:

```bash
printf -v time_str "%02d:%02d" "$rh" "$rm"
```

## Stop the timer

Press `Ctrl+C` — the terminal is restored cleanly.
