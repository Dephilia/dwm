# My dwm build
This reposity is fork from https://aur.archlinux.org/packages/dwm-distrotube-git/


# Dependencies
+ alacritty
+ rofi

Also, you will need to add the following from the AUR:
+ nerd-fonts-complete (optional)
+ https://aur.archlinux.org/packages/libxft-bgra/ (needed for colored fonts and emojis)

Also, if you are building this on an Ubuntu-based system, you need to install libx11-dev and xorg-dev.

# Installing on Arch Linux

All you need to do is download the PKGBUILD from this repository.  Then run the following command:
Do some setting on config.def.h

	git clone https://github.com/Dephilia/dwm-dep
	cd dwm-dep
  sudo make clean install
	

# Running dwm

If you do not use a login manager (such as lightdm) then you can add the following line to your .xinitrc to start dwm using startx:

    exec dwm
	
If you use a login manager (like lightdm), make sure that you have a file called dwm.desktop in your /usr/share/xsessions/ directory.  It should look something like this:

	[Desktop Entry]
	Encoding=UTF-8
	Name=Dwm
	Comment=Dynamic window manager
	Exec=dwm
	Icon=dwm
	Type=XSession

# Adding an autostart file

You will need to create this file and the directory that it is located.  An example autostart.sh is included below:

	#! /bin/bash 
	compton &
	nitrogen --restore &
	dwmblocks &
	
The example autostart.sh above launches the compton compositor, sets the wallpaper with nitrogen and launches dwmblocks to add some widgets to our dwm panel.  Obviously, you would need to install compton and nitrogen to use those programs in your autostart.  And you would need to install [dwmblocks](https://gitlab.com/dwt1/dotfiles/-/tree/master/dwmblocks) to use it.  To use my dwmblocks, you also need to download the scripts found [here](https://gitlab.com/dwt1/dotfiles/-/tree/master/.local%2Fbin).
