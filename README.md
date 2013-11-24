Basic setups:
      0- 101:
         # cp -r <path-to-null-i3-git-clone>/i3 ~/
         # mv ~/.xsession ~/.xsession.old
         # ln -s ~/i3/xsession ~/.xsession

         note on .xsession:
	     SEMI-GNOME MODE (RECOMMENDED): exec dbus-launch --exit-with-session i3 -c ~/i3/config.semi-gnome
             GNOME MODE: exec dbus-launch --exit-with-session i3 -c ~/i3/config.gnome
             PURE MODE:  exec dbus-launch --exit-with-session i3 -c ~/i3/config.pure

	logout and login with 'Default X Session' 

      1- install dependencies:
         # take a look inside i3/APTGET file

      2- lxpanel setup:
         # mv ~/.config/lxpanle ~/.config/lxpanel.old
         # cp -r ~/i3/lxpanel  ~/.config/

      3- Set wallpaper (on pure and semi-gnome mode):
         # nitrogen
         and, preferences > add
         then, pick a wallpaper and <apply>

      4- change statusbar by editing:
         ~/i3/status.sh

      5- change keyboard layout(pure and semi-gnome):
        Look for this line:
        exec --no-startup-id setxkbmap -rules evdev -model pc105 -layout "us,ir" -option "grp:alt_shift_toggle"
        and change the -layout option

# ------------------ SEMI-GNOME MODE (RECOMMENDED MODE) -------------------- #
Best of both worlds.
Keybindings:
    take a look inside ~/i3/config.semi-gnome

# ------------------- PURE MODE -------------------- #
conf file: i3/config.pure

Keybindings:
    take a look inside ~/i3/config.pure

Add/Remove Keyboard Layout:
    change this line:
    exec --no-startup-id setxkbmap -rules evdev -model pc105 -layout "us,ir" -option "grp:alt_shift_toggle"

    inside ~/i3/config
    
pcmanfm mount failiure:
	sudo nano /usr/share/polkit-1/actions/org.freedesktop.udisks.policy
	Find the id:
	org.freedesktop.devicekit.disks.filesystem-mount-system-internal
	Look for the line
	<allow_active>auth_admin_keep</allow_active>
	and replace it with
	<allow_active>yes</allow_active>

# ------------------ GNOME MODE -------------------- #
# NOTE:
#   stable: gnome-session = 3.4.*
#   UNSTABLE (not recommended): gnome-session >= 3.8 
conf file: i3/config.gnome
sudo cp -r ./usr /usr
restart gdm (or lightdm or whatever)
change your desktop to 'i3 GNOME'
login


