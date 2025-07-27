# Godot Preview Binary AUR Package

AUR package for Godot Engine preview/beta builds - automatically updated every 20 days.

## What it does

- Automatically checks for new Godot preview/beta releases every 20 days via GitHub Actions
- Downloads directly from official Godot builds
- Provides a separate installation that doesn't conflict with stable Godot

## Installation

```bash
# Using an AUR helper
yay -S godot-preview-bin

# Manual installation
git clone https://github.com/mlm-games/godot-preview-bin-aur.git
cd godot-preview-bin-aur
makepkg -si
