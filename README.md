# energenie-raspberry-pi
- Forked from [energenie-demo](https://github.com/MiniGirlGeek/energenie-demo)
- Python script with arguments to turn [energenie](https://energenie4u.co.uk) sockets on/off

# Requirments
- [energenie sockets](https://energenie4u.co.uk/catalogue/product/MIHO002)
- [energenie Rasberry Pi shield](https://energenie4u.co.uk/catalogue/product/ENER314-IR)
- Rasberry Pi with `RPi` installed

# Example
To turn sockets 1 and 3 on and 2 off:
```
$ python energenie.py 1=on 2=off 3=on
```

# Example use
I'm using this script to automatically turn on an LED strip above my window to simulate daylight during dark winter mornings... yay London 🎉

Done by adding the following lines to the bottom of my [crontab](https://www.raspberrypi.org/documentation/linux/usage/cron.md) file:
```
# turn led strip on/off
30 7 * * 1-5 python /home/pi/energenie-raspberry-pi/energenie.py 1=on
30 8 * * 1-5 python /home/pi/energenie-raspberry-pi/energenie.py 1=off

# play morning alarm (Edvard Grieg - Morning Mood)
45 7 * * 1-5 omxplayer /home/pi/Downloads/morning.mp3
```
