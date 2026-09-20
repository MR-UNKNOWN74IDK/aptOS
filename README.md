# aptOS

An apt-syntax wrapper for pacman, with automatic AUR helper support.

`aptOS` lets you run familiar apt-style commands under a `pkg` namespace —
`aptOS pkg install`, `aptOS pkg remove`, `aptOS pkg upgrade`, and so on — on
any pacman-based system. When run as a normal user it auto-detects an
installed AUR helper (yay, paru, pikaur, aurman, pacaur, aura, trizen) and
routes through it automatically, so AUR packages are reachable too, not
just official repo packages.

> Renamed from `aptyay`. If you have the old `aptyay` package installed,
> installing `aptos` will replace it automatically.

## Install

```bash
git clone https://github.com/MR-UNKNOWN74IDK/aptOS.git
cd aptOS
makepkg -si
```

## Usage

```bash
aptOS pkg install firefox      # repo + AUR, via your detected helper
aptOS pkg search waybar
aptOS pkg upgrade -y
aptOS pkg autoremove
sudo aptOS pkg install firefox # forces plain pacman, skips AUR
```

Run `aptOS pkg --help` for the full command and option list, including
which apt features have no pacman equivalent and why.

## Testing status

This has been tested and confirmed working on **systemd-based Arch Linux**
systems (vanilla Arch, and systemd-based derivatives like Manjaro and
EndeavourOS).

It has **not** been tested on non-systemd-init Arch-based distributions
(e.g. Artix Linux running OpenRC, runit, s6, or dinit). Nothing in aptOS
is intentionally systemd-specific — it only shells out to `pacman` and
optional AUR helpers — but this hasn't been verified in practice.

## Contributing

Pull requests are welcome, especially reports or fixes confirming aptOS
works correctly on non-systemd-init Arch-based systems. If you've run it
successfully (or found something broken) on Artix or another init system,
please open a PR or issue describing what you tested and the result.

## License

AGPLv3. Copyright (C) 2026 MR_UNKNOWN74IDK <mr.unknown74idk@proton.me>. See `LICENSE`.
