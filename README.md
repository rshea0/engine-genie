![Tuneup PRIME](img/tuneup-prime.png)

#### A library management tool for Denon Engine PRIME 🎧

&nbsp;&nbsp;_by [SHAYDED](http://shayded.com)_

- 🚀 [Installation](#-installation)
- ❓ [How To Use](#-how-to-use)
- 🔨 [Commands](#-commands)

## 🌟 Features

- Easy to use graphic interface
- Smart playlists
  - Generate playlists based off of easily configurable rules
  - Filter tracks based on album, file type, and more
  - Use different operators to filter attributes including Regex
  - Logically group filters with `and` & `or`
- Library relocation
  - Relocate missing tracks
  - Provide a folder to search for tracks in
- Imports playlists created on smart consoles like the Prime 4 or SC6000
- Automatically backs up library before running
- Supports Engine 1.6.x
- Cross platform - Windows & macOS

If there's a feature you'd like added that would be useful to you, please open a [feature request](https://github.com/rshea0/enjinn/issues/new/choose)!

## 🚀 Installation

ENJINN can be purchased on [Gumroad](https://gum.co/enjinn).

After purchasing, simply download and run the installer.

#### Updating

```
$ enjinn update
```

> ENJINN will notify you when an update is available.

### npm version

You can also install ENJINN with `npm`.

_You will still need to [purchase a license key](https://gum.co/enjinn) to use all features._

Requires [NodeJS v14+](https://nodejs.org/en/)

```
$ npm install -g enjinn
```

#### Updating

```
$ npm install -g enjinn@latest
```

## ❓ How To Use

ENJINN is a command line app, which means you will need to run it from your terminal.

> ⚠️ **Engine must be closed when running ENJINN!**

Depending on your OS, here's how you can open up a terminal:

#### Windows 10

- Press `Windows Key` and `R` on your keyboard
- Type `cmd` and hit `enter`

#### macOS

- Press `Command` and `space` on your keyboard
- Type `terminal` and hit `enter`

Once your terminal is open, simply run the `enjinn` command to view the help info.

_Only type the text after the `$`_

```
$ enjinn
```

> To stop ENJINN in the middle of running a command, press `ctrl+c`.

[Available commands](#-commands)

### Activating

To use all features of ENJINN, you need to activate it with a [license key](https://gum.co/enjinn).

> ENJINN only requires an internet connection during activation and never again.

To activate ENJINN, run the `activate` command. Paste in your license key when prompted and you're all set!

```
$ enjinn activate
```

### Free vs Paid

The free version has several restrictions:

- Smart playlists: Up to 5 playlists, no nested filters
- Relocate: Basic macthing only. Premium will add the ability to fix individual tracks as well as handle renamed files.
- Playlist import: Premium only.

### Library configuration

The first time you run a command, it will ask you to enter the location of your Engine library.

If you would like to change this later, you can edit the config file.

In the future, you'll be able to specify multiple Engine libraries and even switch between them (possibly, let me know if you think this would be useful).

#### Config file locations:

- Windows: `%LOCALAPPDATA%\enjinn\config.yaml`
- macOS: `~/.config/enjinn/config.yaml`

## 🔨 Commands

- 🧠 [`smart` - Generate smart playlists](#-smart)
- 🔍 [`relocate` - Relocate missing tracks](#-relocate)
- 📼 [`import-ext` - Import playlists from external libraries](#-import-ext)

### 🧠 Smart

Generates smart playlists based off a config file located in your Engine library folder.

```
$ enjinn smart
```

To configure the smart playlists, place a file called `enjinn.yaml` in your Engine library folder. See the [examples](examples/enjinn.example.yaml) to learn how to define playlists.

If a playlist already exists with the same name as one of your smart playlists **IT WILL BE OVERWRITTEN**. In most cases this is desired, as you'll want to update your smart playlists.

### 🔍 Relocate

Finds tracks in your library that are missing, because you've moved the files to a new folder.

```
$ enjinn relocate
```

ENJINN will scan your library for tracks that are missing on disk. It will then ask you to specify a folder to search for your tracks in. It will also search up to 5 subfolders deep. After searching, it will print out the relocated tracks and their new paths.

Currently, the filenames have to be the same, but soon you'll be able to specify rules for matching filenames as well as rename individual files.

### 📼 Import External

Imports playlists created on smart consoles like the Prime 4 or SC6000.

```
$ enjinn import-ext
```

ENJINN will look for USB drives that contain Engine libraries. It will ask you to select which drive to import from. After selecting a drive, it will ask you which playlists you want to import.
