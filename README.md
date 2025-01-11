# OhMyPoshArchGuide

Hello, this is a short and casual (unofficial) guide to installing [oh-my-posh](https://ohmyposh.dev/) on Arch Linux and Arch-like systems such as EndeavourOS. This guide assumes the user is using some version of KDE Konsole as their terminal emulator.

![Demonstration Image](https://github.com/zzz-Ricky/OhMyPoshArchGuide/blob/main/Images/Screenshot_20250111_153546.png?raw=true)

*(Tested on EndeavourOS, KDE Plasma 6.2.5 with [KDE Rounded Corners](https://github.com/matinlotfali/KDE-Rounded-Corners), [ForceBlur](https://github.com/taj-ny/kwin-effects-forceblur), and [Kröhnkite](https://github.com/esjeon/krohnkite).)*

## Installation

### Installing Oh My Posh

To start things off, we need to install Oh My Posh and its dependencies.

- The simplest way to install this application is using the Arch User Repository (AUR):
  - [Oh My Posh AUR package](https://aur.archlinux.org/packages/oh-my-posh)

```bash
yay -S oh-my-posh
```

- Alternatively, you can install Oh My Posh directly from the source. This method is recommended if you wish to avoid using the AUR:
  - Follow the [official installation instructions](https://ohmyposh.dev/docs/installation/linux).

### Testing the Installation

To verify that Oh My Posh has been installed correctly, run the following command in the terminal:

```bash
oh-my-posh
```

If the installation was successful, you should see output similar to the following screenshot:

![Example of successful installation output](https://github.com/zzz-Ricky/OhMyPoshArchGuide/blob/main/Images/Screenshot_20250111_155306.png?raw=true)
The more observant amoung you may notice that I already have oh-my-posh installed. To prevent the possibility of time travel paradoxes, please disregard the console decorations and focus on the text.

### Modifying `.bashrc`

The `.bashrc` file is a hidden script that automatically executes whenever you log in or start a new terminal session. We will add a command to this file to start Oh My Posh on terminal launch.

1. Locate the `.bashrc` file in your home directory (e.g., `/home/{username}/.bashrc`).
   - Use a graphical file manager like Dolphin to find this file. ![.bashrc located using dolphin](https://github.com/zzz-Ricky/OhMyPoshArchGuide/blob/main/Images/Screenshot_20250111_160356.png?raw=true)
   - You can also edit it directly in the terminal using a text editor like Nano:

   ```bash
   nano ~/.bashrc
   ```

2. Append the following line to the end of the `.bashrc` file:

   ```bash
   eval "$(oh-my-posh --init --shell bash --config /usr/share/oh-my-posh/themes/takuya.omp.json)"
   ```

3. Save your changes and exit the editor.

4. Reload the `.bashrc` file to apply the changes:

   ```bash
   source ~/.bashrc
   ```

### Installing Nerd Fonts

Some Oh My Posh themes may display graphical errors, such as missing icons or decorative elements. To resolve this, install a proper Nerd Font.

A Nerd Font is a patched font that includes a wide range of icons, symbols, and glyphs, enhancing terminal and development tools' visual functionality.

For this guide, we will install a patched version of Source Code Pro:

```bash
sudo pacman -Syu ttf-sourcecodepro-nerd
```

#### Setting the Font in KDE Konsole

1. Open Konsole and navigate to **Settings > Edit Current Profile > Appearance**.
2. Select a font patched with Nerd Font support (e.g., Source Code Pro Nerd Font).
3. Save and apply your changes.

![Step1](https://github.com/zzz-Ricky/OhMyPoshArchGuide/blob/main/Images/Screenshot_20250111_161737.png?raw=true)
![Step2](https://github.com/zzz-Ricky/OhMyPoshArchGuide/blob/main/Images/Screenshot_20250111_161757.png?raw=true)
![Step3](https://github.com/zzz-Ricky/OhMyPoshArchGuide/blob/main/Images/Screenshot_20250111_161823.png?raw=true)

### Conclusion

By now, you should have a functional installation of Oh My Posh on your Arch Linux system. You can enjoy your customized terminal or continue reading to learn how to further customize Oh My Posh themes.

---

## Customization

When you install Oh My Posh from the AUR, it includes a variety of pre-installed themes. By default, these themes are located in:

```bash
/usr/share/oh-my-posh/themes/
```

*(Placeholder for screenshot of the themes directory)*

To change themes, modify the configuration command in your `.bashrc` file. For example:

```bash
eval "$(oh-my-posh --init --shell bash --config /usr/share/oh-my-posh/themes/takuya.omp.json)"
```

Replace `takuya.omp.json` with the desired theme. For instance, to use the "aliens" theme, update the line to:

```bash
eval "$(oh-my-posh --init --shell bash --config /usr/share/oh-my-posh/themes/aliens.omp.json)"
```

After saving the changes, run:

```bash
source ~/.bashrc
```

to apply the new theme.

---

Enjoy your beautifully customized terminal!

