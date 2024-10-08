# Custom Aliases for Linux (tested on Arch)

This repository contains a set of useful custom aliases for improving your Linux experience. These aliases cover various tasks like displaying IP addresses, removing unused dependencies, checking for package upgrades, sourcing `.bashrc`, and showing the weather forecast for a specific city.

## Aliases

### 1. Print your IP address

To display your IPv4 or IPv6 address:

```bash
alias ipv4="ip addr show | grep 'inet ' | grep -v '127.0.0.1' | cut -d' ' -f6 | cut -d/ -f1"
alias ipv6="ip addr show | grep 'inet6 ' | cut -d ' ' -f6 | sed -n '2p'"
```

### 2. Remove unused dependencies

To remove unused or orphaned dependencies on Arch Linux:

```bash
alias autorem='orphans=$(pacman -Qdtq); [ -z "$orphans" ] && echo "There are no orphaned packages" || sudo pacman -Rsc $orphans'
```

### 3. Show potential upgrades (requires yay)

To check for available upgrades using `yay`:

```bash
alias potupg='yay -Sy &> /dev/null && yay -Qu'
```

### 4. Source `.bashrc`

To quickly source your `.bashrc` file:

```bash
alias srcbsh='source ~/.bashrc && echo ".bashrc sourced!"'
```

### 5. Show weather forecast

To get the weather forecast for a specific city (replace `exampleCity` with your city):

```bash
alias weather='curl wttr.in/exampleCity | head -n -1'
```

---

## Usage

Copy these aliases to your `.bashrc` or `.zshrc` file and run the following command to apply them:

```bash
source ~/.bashrc
```
