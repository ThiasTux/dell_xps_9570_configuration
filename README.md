# Dell XPS 9570 Configuration

Configuration of linux distros on Dell XPS 9570

## External monitor with scaling (Xorg)

User xrandr for setting displays:
	
	xrandr --output eDP1 --auto --output DP3 --mode 1920x1080 --panning 3840x2160+3840+0 --scale 2x2 --right-of eDP1

Change `eDPI` and `DP3` accordingly with the output of `xrandr`.
In order to fix cursor flickers when `xrandr` scales, create a file `20-intel.conf`:

	Section "Device"
   		Identifier  "Intel Graphics"
   		Driver      "intel"
	EndSection

In the folders:
	
	/etc/X11/xorg.conf.d/ (for Archlinux)
	/usr/share/X11/xorg.conf.d/ (for Ubuntu)

And reboot. Gnome allows to execute those commands once logged in. KDE to be tested.

