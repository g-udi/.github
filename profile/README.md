# g-udi

g-udi is a collection of tools for making a macOS and Unix-like development environment reproducible, comfortable, and inspectable. The projects cover machine bootstrap, shell frameworks, prompt themes, and desktop/status-bar widgets.

The common goal is simple: a fresh machine should be able to become a working environment from versioned configuration, and the tools that keep it running should be small enough to understand.

## Project Map

### Machine Setup

| Repository | Purpose |
|------------|---------|
| [gaudi](https://github.com/g-udi/gaudi) | Workstation bootstrapper for macOS, Debian/Ubuntu, Fedora, Arch and openSUSE: installs prerequisites, templates, software from [Brewfiles](https://docs.brew.sh/Brew-Bundle-and-Brewfile) and package lists, configuration scripts and dotfiles, with backups and template checks through the `gaudi` CLI. |
| [gaudi-templates](https://github.com/g-udi/gaudi-templates) | Public templates used by Gaudi to define Brewfiles, package lists, hooks, machine configuration, and the dotfiles to back up. |
| [gaudi-helper](https://github.com/g-udi/gaudi-helper) | Shell helper that watches successful package-manager installs and keeps Gaudi template package lists updated. |

### Shell Frameworks

| Repository | Purpose |
|------------|---------|
| [gaudi-shell](https://github.com/g-udi/gaudi-shell) | Cross-shell framework for aliases, plugins, completions, and themes across Bash and Zsh, evolved from gaudi-bash. Its command is `gshell`. |
| [gaudi-bash](https://github.com/g-udi/gaudi-bash) | Bash-focused shell framework and loader, the predecessor of gaudi-shell. Its command is `gbash`. |
| [gaudi-bash-components](https://github.com/g-udi/gaudi-bash-components) | Component container for aliases, plugins, completions, and themes. |
| [gaudi-bash-aliases](https://github.com/g-udi/gaudi-bash-aliases) | Bash alias components. |
| [gaudi-bash-completions](https://github.com/g-udi/gaudi-bash-completions) | Bash completion components. |
| [gaudi-bash-plugins](https://github.com/g-udi/gaudi-bash-plugins) | Bash plugin components. |
| [gaudi-bash-themes](https://github.com/g-udi/gaudi-bash-themes) | Bash theme components. |
| [gaudi-theme](https://github.com/g-udi/gaudi-theme) | Modular asynchronous Bash prompt theme with segments for Git, runtimes, cloud context, Docker, system state, and more. |

### Desktop and Status Bars

| Repository | Purpose |
|------------|---------|
| [gaudi-sketchybar](https://github.com/g-udi/gaudi-sketchybar) | macOS SketchyBar setup for notifications, system stats, yabai spaces, and app-local status. |
| [gaudiBar.ubersicht.widget](https://github.com/g-udi/gaudiBar.ubersicht.widget) | Responsive Übersicht menu bar made from configurable widgets. |
| [gaudiDesktop.ubersicht.widgets](https://github.com/g-udi/gaudiDesktop.ubersicht.widgets) | Übersicht desktop dashboard for productivity inboxes, metrics, GitHub, and calendar cards. |

## How The Pieces Fit

Gaudi starts with the machine:

1. [gaudi](https://github.com/g-udi/gaudi) bootstraps the workstation.
2. [gaudi-templates](https://github.com/g-udi/gaudi-templates) defines what gets installed and configured.
3. [gaudi-helper](https://github.com/g-udi/gaudi-helper) keeps those lists current as you install new tools.
4. [gaudi-shell](https://github.com/g-udi/gaudi-shell), which Gaudi's setup offers as the shell helper, shapes the interactive terminal; [gaudi-bash](https://github.com/g-udi/gaudi-bash) and the shell component repos are the Bash-only framework it evolved from.
5. [gaudi-theme](https://github.com/g-udi/gaudi-theme), [gaudi-sketchybar](https://github.com/g-udi/gaudi-sketchybar), and the Übersicht widgets surface useful context while you work.

## Contribution Guidelines

Contributions are welcome across the public repos. The short version:

- Open an issue first for behavioral changes, new public APIs, or larger refactors.
- Keep changes scoped to the repo and feature being touched.
- Match the existing shell, JavaScript, CSS, and documentation style.
- Add or update smoke tests when behavior changes.
- Avoid committing machine-local files, secrets, generated runtime output, or private templates.
- Run the repo's documented validation command before opening a pull request.

See the organization-wide [contributing guide](https://github.com/g-udi/.github/blob/master/CONTRIBUTING.md) for details.

## Development Standards

Across the organization, we prefer:

- Small, composable shell scripts with strict quoting and predictable failure modes.
- Idempotent installers and profile updates.
- Clear environment-variable based configuration.
- Portable defaults with macOS-first behavior where a project is explicitly macOS-focused.
- README files that explain the user workflow, not only the implementation.

## Start Here

- Setting up a machine: [gaudi](https://github.com/g-udi/gaudi)
- Managing shell components: [gaudi-shell](https://github.com/g-udi/gaudi-shell)
- Maintaining package templates while you work: [gaudi-helper](https://github.com/g-udi/gaudi-helper)
- Building a prompt: [gaudi-theme](https://github.com/g-udi/gaudi-theme)
- Building a macOS status bar: [gaudi-sketchybar](https://github.com/g-udi/gaudi-sketchybar)
