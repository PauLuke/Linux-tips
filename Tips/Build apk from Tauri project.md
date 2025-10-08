## Prerequisites

In order to get started building your project with Tauri you’ll first need to install a few dependencies:

- System Dependencies
- Rust
- Configure for Mobile Targets (only required if developing for mobile)

### System Dependencies:

To install the System dependencies use the following command:

```
sudo pacman -Syu

sudo pacman -S --needed \
  webkit2gtk-4.1 \
  base-devel \
  curl \
  wget \
  file \
  openssl \
  appmenu-gtk-module \
  libappindicator-gtk3 \
  librsvg \
  xdotool
```

### Rust:

Use this command to install Rust:

```
yay -S rustup
```

### Configure for Mobile Targets:

Android:

```
rustup target add aarch64-linux-android armv7-linux-androideabi x86_64-linux-android
```

IOS:

```
rustup target add aarch64-apple-ios x86_64-apple-ios aarch64-apple-ios-sim
```

## Create a new project

```
npm create tauri-app@latest 
```

Then

```
cd tauri-app
npm install
npm run tauri dev
```

Inside your project you will find a directory called "src". This is the place to put your web project files.

## Building a apk

```
npm run tauri android build -- --apk --target aarch64 --target armv7
```
At the end the command will say where you will find the apk.
