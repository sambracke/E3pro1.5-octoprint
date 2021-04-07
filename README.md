# install klipper + compile firmware for Ender 3 pro "1.5" (4.2.2 mainboard)
`
cd
git clone https://github.com/KevinOConnor/klipper
./klipper/scripts/install-octopi.sh
cd klipper
wget https://raw.githubusercontent.com/sambracke/E3pro1.5-octoprint/master/klipper/.config
make
`
# copy ~/klipper/out/klipper.bin to empty SD card, power on printer with the SD card containing klipper.bin

# set up Octoprint for Klipper
Install OctoKlipper plugin
In Octoprint settings:

Printer > Serial Connection > General add '/tmp/printer' to 'Additional serial ports' and select it as serial port.
Printer > Serial Connection > Behavior select 'Cancel any ongoing prints but stay connected to the printer'

# tune Esteps for extruder
do an extrusion test, in Klipper configuration change [extruder] setting 'rotation_distance'
