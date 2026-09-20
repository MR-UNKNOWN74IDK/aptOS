# aptOS

An apt-syntax wrapper for pacman, with automatic AUR helper support.

`aptOS` lets you run familiar apt commands — `apt install`, `apt remove`,
`apt upgrade`, and so on — on any pacman-based system. When run as a normal
user it auto-detects an installed AUR helper (yay, paru, pikaur, aurman,
pacaur, aura, trizen) and routes through it automatically, so AUR packages
are reachable through apt syntax too, not just official repo packages.

## Install

```bash
git clone https://github.com/MR-UNKNOWN74IDK/aptOS.git
cd aptOS
makepkg -si
```

This installs the `aptOS` binary plus `apt`/`apt-get` symlinks, so you can
just type `apt install hyprland`, `apt upgrade`, etc.

## Usage

```bash
apt install hyprland      # repo + AUR, via your detected helper
apt search waybar
apt upgrade -y
apt autoremove
apt rdepends firefox       # aptOS extra: reverse dependency lookup
sudo apt install hyprland  # forces plain pacman, skips AUR
```

Run `apt --help` for the full command and option list, including which apt
features have no pacman equivalent and why.

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
