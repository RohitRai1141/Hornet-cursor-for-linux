# 🐝 Hornet Cursor Theme for Linux

A lightweight, stylish **Hornet-inspired animated cursor theme** for Linux 🖱️  
Supports **GNOME**, **Hyprland**, **Wayland**, and **X11**.  
You can either use the **prebuilt theme** (ready to go) or **build your own** from `.ani` / `.cur` files.

---

## 🚀 Installation Options

### **Option A – Use Prebuilt Theme (Recommended for Most Users)**

If you just want the ready-to-use theme:

```bash
# 1. Clone the repository
git clone https://github.com/<your-username>/Hornet-cursor-for-linux.git
cd Hornet-cursor-for-linux

# 2. Extract the Hornet theme to your user icons folder
unzip Hornet-cursor-theme.zip -d ~/.icons/

# 3. Set correct permissions
chmod -R a+r ~/.icons/Hornet

# 4. Refresh the icon cache
gtk-update-icon-cache -f -t ~/.icons/Hornet || true

# 5. Apply Hornet cursor for this session
export XCURSOR_THEME=Hornet
export XCURSOR_SIZE=24

# 6. Persist across reboots
grep -qx 'export XCURSOR_THEME="Hornet"' ~/.profile 2>/dev/null || echo 'export XCURSOR_THEME="Hornet"' >> ~/.profile
grep -qx 'export XCURSOR_SIZE=24' ~/.profile 2>/dev/null || echo 'export XCURSOR_SIZE=24' >> ~/.profile

# 7. Restart nwg-look or your theme manager
pkill -f nwg-look || true
nwg-look &

# 8. Log out and back in (or reboot)
