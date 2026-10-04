# Breeze Titleless

A modified version of KDE's [Breeze](https://invent.kde.org/plasma/breeze) window decoration for Plasma 6.

**Breeze Titleless** keeps the standard Breeze title bar and window controls, but removes the window title text.

## Changes

* Removes the window title text.
* Keeps the title bar, minimize, maximize, and close buttons.
* Installs as a separate decoration alongside the original Breeze.
* Plugin ID: `org.kde.breeze.titleless`
* Plugin name: **Breeze Titleless** / **Brisa ST**

## Building

Clone, build, and install the decoration:

```bash
sudo pacman -S cmake extra-cmake-modules
git clone https://github.com/RulOfficial/breeze.git
cd breeze
cmake -B build -S . -DCMAKE_INSTALL_PREFIX=/usr
cmake --build build
sudo cmake --install build
cd ~
rm -rf breeze
sudo pacman -Rs cmake extra-cmake-modules
```

Then select **Breeze Titleless** in **System Settings → Window Decorations**.

## Uninstalling

Just delete the plugin and then reinstall breeze.

```bash
sudo rm -v /usr/lib/qt6/plugins/org.kde.kdecoration3/org.kde.breeze.titleless.so
sudo pacman -S breeze
```

Based on KDE Breeze. See the [original Breeze repository](https://github.com/KDE/breeze) for the upstream project.
