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
✅ After reboot, Hornet will be active everywhere.
If you’re using Hyprland or GNOME, see specific tweaks below.

Option B – Build From .ani/.cur Files
If you have a Windows cursor pack (.ani, .cur) and want to convert it yourself:

bash
Copy code
# 1. Clone the repo
git clone https://github.com/<your-username>/Hornet-cursor-for-linux.git
cd Hornet-cursor-for-linux

# 2. Make installer executable
chmod +x install.sh

# 3. Run installer with your cursor source folder
bash install.sh ~/Downloads/HornetSource

# 4. (Optional) Fix preview icons
chmod +x fix-preview.sh
./fix-preview.sh
The script will:

Convert .ani / .cur files into .cursor format

Create standard cursor aliases (left_ptr, xterm, watch, etc.)

Generate index.theme

Update your GTK cache

Apply and persist the theme

🧰 Prerequisites
On Arch (other distros: install equivalents):

bash
Copy code
sudo pacman -Syu --needed git bash coreutils gtk3 imagemagick xorg-xcursorgen python-pipx
pipx install win2xcur
For AUR users:

bash
Copy code
paru -S win2xcur
🪟 Environment Setup (for all compositors)
Hyprland
Add to ~/.config/hypr/hyprland.conf:

ini
Copy code
env = XCURSOR_THEME,Hornet
env = XCURSOR_SIZE,24
Then:

bash
Copy code
hyprctl reload
GNOME / GTK
Edit or create:

bash
Copy code
~/.config/gtk-3.0/settings.ini
Add:

ini
Copy code
[Settings]
gtk-cursor-theme-name=Hornet
gtk-cursor-theme-size=24
⚡ Troubleshooting
Cursor not changing in browser or apps
Restart them after applying the theme.
Electron apps (VSCode, Discord, etc.) cache cursor themes at startup.

One cursor missing in nwg-look preview
Run:

bash
Copy code
cd ~/.icons/Hornet/cursors
ln -sf rowresize sb_v_double_arrow
ln -sf colresize h_double_arrow
ln -sf colresize left_side
ln -sf resize-nw top_left_corner
gtk-update-icon-cache -f -t ~/.icons/Hornet
Verify theme loaded
bash
Copy code
echo $XCURSOR_THEME
file ~/.icons/Hornet/cursors/left_ptr
# should say: Xcursor data version 1.0
🧹 Uninstall
bash
Copy code
rm -rf ~/.icons/Hornet
sed -i '/XCURSOR_THEME="Hornet"/d' ~/.profile
sed -i '/XCURSOR_SIZE=24/d' ~/.profile
gtk-update-icon-cache -f -t ~/.icons || true
Reboot or log out/in.

🧠 Notes for Developers
Compatible with both X11 and Wayland (Hyprland, GNOME, Sway).

You can easily adapt the script to other cursor packs.

Feel free to fork, modify, or package for AUR.

📜 License
MIT License © 2025 [Your Name]

💬 Credits
Original .ani / .cur design: Hornet Cursor Pack

Conversion tools: win2xcur

Theme management: nwg-look

🐝 Enjoy your sleek Hornet cursor buzzing across your Linux desktop!

yaml
Copy code

---

### ✅ What to do next
1. Copy the above and save as:
   ```bash
   nano ~/Documents/GitHub/Hornet-cursor-for-linux/README.md
Replace <your-username> with your GitHub username.

Commit and push:

bash
Copy code
cd ~/Documents/GitHub/Hornet-cursor-for-linux
git add README.md
git commit -m "Added complete usage guide to README"
git push
