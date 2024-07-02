# tmux2-zjstatus-layout

<img width="986" alt="Screenshot 2024-07-02 at 10 36 17 PM" src="https://github.com/starkovv/tmux2-zjstatus-layout/assets/654646/88fd4901-f70e-4a1c-98d3-7efd58f1deb1">
This repository contains the "tmux2" styled layout for the Zjstatus plugin used with Zellij. This layout is designed to work best with the "solarized dark" terminal color theme.

## Features

- Clean and modern status bar design
- Host OS icon, session name, and mode displayed on the left
- Centered tab names with active tab highlighting
- Right-aligned layout swap indicator and current date/time
- Dynamic mode indicators for various Zellij modes
- Customizable through KDL configuration

## Installation

1. **Download Zjstatus:**
   Follow the installation instructions from the [Zjstatus GitHub repository](https://github.com/dj95/zjstatus).

2. **Copy Layout:**
   Place the provided `default.kdl` configuration file in your Zellij layouts directory:
   ```sh
   mkdir -p ~/.config/zellij/layouts
   cp default.kdl ~/.config/zellij/layouts/default.kdl
   ```

3. **Apply the Layout:**
   Start Zellij with the new layout:
   ```sh
   zellij --layout default
   ```
   Or just run:
   ```sh
   zellij
   ```
   

## Configuration

Here is the `default.kdl` layout configuration:

```kdl
layout {
  default_tab_template {
    children
      pane size=1 borderless=true {
        plugin location="file:~/.local/share/zellij/plugins/zjstatus.wasm" {
          format_left  "#[bg=green,fg=black] {command_host_os_icon} {session} {mode}"
          format_center "{tabs}"
          format_right "#[bg=green,fg=black] {swap_layout} │ {datetime} "
          format_space  "#[bg=green]"

          mode_normal        "#[bg=green,fg=black]│#[bg=green,fg=black] NORMAL "
          mode_locked        "#[bg=green,fg=green]│#[bg=red,fg=black]  LOCKED "
          mode_resize        "#[bg=green,fg=green]│#[bg=magenta,fg=black] RESIZE "
          mode_pane          "#[bg=green,fg=green]│#[bg=magenta,fg=black] PANE "
          mode_tab           "#[bg=green,fg=green]│#[bg=magenta,fg=black] TAB "
          mode_scroll        "#[bg=green,fg=green]│#[bg=magenta,fg=black] SCROLL "
          mode_enter_search  "#[bg=green,fg=green]│#[bg=magenta,fg=black] ENTER_SEARCH "
          mode_search        "#[bg=green,fg=green]│#[bg=magenta,fg=black] SEARCH "
          mode_rename_tab    "#[bg=green,fg=green]│#[bg=magenta,fg=black] RENAME_TAB "
          mode_rename_pane   "#[bg=green,fg=green]│#[bg=magenta,fg=black] RENAME_PANE "
          mode_session       "#[bg=green,fg=green]│#[bg=magenta,fg=black] SESSION "
          mode_move          "#[bg=green,fg=green]│#[bg=magenta,fg=black] MOVE "
          mode_prompt        "#[bg=green,fg=green]│#[bg=magenta,fg=black] PROMPT "
          mode_tmux          "#[bg=green,fg=green]│#[bg=magenta,fg=black] TMUX "

          tab_normal "#[bg=green,fg=black] #[bg=green,fg=black]{name} {sync_indicator}{fullscreen_indicator}{floating_indicator}#[bg=green,fg=black]"
          tab_active "#[bg=black,fg=green] #[bg=black,fg=green]{name} {sync_indicator}{fullscreen_indicator}{floating_indicator}#[bg=black,fg=green]"

          tab_sync_indicator       "󰓦 "
          tab_fullscreen_indicator "󱟱  "
          tab_floating_indicator   "󰉈 "

          command_host_os_icon_command "sh -c \"echo $(uname -s | grep -qi 'darwin' && echo '󰀵')$(uname -s | grep -qi 'linux' && echo '')$(uname -s | grep -qi 'nt' && echo '󰖳')\""
          command_host_os_icon_format "{stdout}"
          command_host_os_icon_interval "0"
          command_host_os_icon_rendermode "static"

          datetime          "{format}"
          datetime_format   "%d-%m-%Y %H:%M"
          datetime_timezone "Europe/Berlin"
        }
      }
  }
}
```

## License

This project is licensed under the MIT License.

## Contributing

Feel free to submit a pull request or open an issue if you have any suggestions or find any bugs.

## Acknowledgments

Thanks to [dj95](https://github.com/dj95) for the original Zjstatus plugin and the inspiration for this layout.
