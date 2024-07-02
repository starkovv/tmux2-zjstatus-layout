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
   

## License

This project is licensed under the MIT License.

## Contributing

Feel free to submit a pull request or open an issue if you have any suggestions or find any bugs.

## Acknowledgments

Thanks to [dj95](https://github.com/dj95) for the original Zjstatus plugin and the inspiration for this layout.
