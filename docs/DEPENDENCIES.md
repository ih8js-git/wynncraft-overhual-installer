# System Dependencies

On Linux, the installer uses [Dioxus](https://dioxuslabs.com/) with a native desktop webview and windowing system. Because of dynamic linking, certain system libraries must be installed on your system.

---

## Runtime Dependencies

If you are running a pre-built binary on Linux, ensure the following packages are installed for your distribution:

### Arch Linux
```bash
sudo pacman -S xdotool gtk3 webkit2gtk-4.1 openssl
```

### Debian / Ubuntu
```bash
sudo apt update
sudo apt install -y libxdo3 libgtk-3-0 libwebkit2gtk-4.1-0 libssl3
```

### Fedora
```bash
sudo dnf install libxdo gtk3 webkit2gtk4.1 openssl
```

---

## Build Dependencies (Compiling from Source)

If you are compiling the installer from source, you will need the C compiler, development header packages (`-dev` / `-devel`), and `pkg-config`:

### Arch Linux
```bash
sudo pacman -S base-devel xdotool gtk3 webkit2gtk-4.1 openssl
```

### Debian / Ubuntu
```bash
sudo apt update
sudo apt install -y gcc pkg-config libglib2.0-dev libgtk-3-dev libssl-dev \
    libjavascriptcoregtk-4.1-dev libsoup-3.0-dev libwebkit2gtk-4.1-dev libxdo-dev
```

### Fedora
```bash
sudo dnf install gcc pkg-config glib2-devel gtk3-devel openssl-devel \
    webkit2gtk4.1-devel libsoup3-devel libxdo-devel
```

---

## Building the Project

Once the dependencies are installed and you have [Rust](https://rustup.rs/) installed:

```bash
cargo build --release
```

The compiled binary will be located at `target/release/installer`.
