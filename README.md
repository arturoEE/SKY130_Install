# SKY130_Install
Instructions to self on how to install sky130, xschem, magic

0. Prerequisites\
`open software-properties-gtk`\
Check the Source Code box \
`sudo apt install libgtk-3-dev build-essential`


1. Install Magic\
`git clone https://github.com/RTimothyEdwards/magic.git`\
`cd magic`\
`sudo ./configure`\
`sudo make`\
`sudo make install`

2. Install Open PDK\
`cd ~`\
`./configure --enable-sky130-pdk --enable-sram-sky130`\
`sudo make`\
`sudo make install`

3. Install SKY130\
`cd sky130`\
`sudo make`\
`sudo make install`

4. Install ngspice\
`sudo apt install ngspice`

5. Install gaw\
`wget http://download.tuxfamily.org/gaw/download/gaw3-20200922.tar.gz`\
`tar -xf gaw3-20200922.tar.gz`\
`cd gaw3-20200922`\
`./configure`\
`make -j$(nproc)`\
`sudo make install`\
`gaw`\
close gaw\
`gedit ~/.gaw/gawrc`\
change `up_listenPort = 0` to `up_listenPort = 2020`

6. Install Xschem\
`sudo apt build-dep xschem`\
`sudo apt install xterm graphicsmagick ghostscript`\
`cd ~`\
`git clone https://github.com/StefanSchippers/xschem.git`\
`./configure`\
`make -j$(nproc)`\
`sudo make install`\
`cd ~`\
`sudo install -o $USER -d /usr/local/share/{sky130_fd_pr,xschem_sky130}`\
`git clone https://foss-eda-tools.googlesource.com/skywater-pdk/libs/sky130_fd_pr /usr/local/share/sky130_fd_pr`\
`git clone https://github.com/StefanSchippers/xschem_sky130 /usr/local/share/xschem_sky130`\
`mkdir xschem_schematics`\
`touch xschemrc`\
`gedit xschemrc`\

Paste in xschemrc:\
`set XSCHEM_LIBRARY_PATH {}`\
`append XSCHEM_LIBRARY_PATH :${XSCHEM_SHAREDIR}/xschem_library`\
`append XSCHEM_LIBRARY_PATH :/usr/local/share/xschem_sky130`
