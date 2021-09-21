## Build the SD Card Image

A ready-to-use SD card image of RaspiBlitz is provided by us for download, to get everybody started quickly. But if you want to build that image yourself - here is a quick guide:

* Get a latest RaspiOS 64-bit: [DOWNLOAD](https://downloads.raspberrypi.org/raspios_arm64/images).
* Write the image to an SD card: [TUTORIAL](https://www.raspberrypi.org/documentation/installation/installing-images/README.md).
* Add a file called `ssh` to the root of the SD card when mounted on your laptop to enable SSH login.
* Start the card on a Raspi and login via SSH with `ssh pi@[IP-OF-YOUR-RASPI]`. Password is `raspberry`.

Now you are ready to start the SD card build script (check the code to see if the installation and config are OK for you). Copy the following command into your terminal and execute:

`wget https://raw.githubusercontent.com/rootzoll/raspiblitz/v1.7/build_sdcard.sh && sudo bash build_sdcard.sh`

As you can see from the URL, you can find the build script in this Git repo under `build_sdcard.sh`. You can check what gets installed and configured in detail. Feel free to post improvements as pull requests.

The whole build process takes a while. At the end the LCD drivers get installed and a reboot is needed. A user `admin` is created during the process. Remember the default password is now `raspiblitz`. You can login per SSH again - this time use admin: `ssh admin@[IP-OF-YOUR-RASPI]`. The install dialog of the RaspiBlitz should automatically start. If you do not want to continue with the installation at this moment and use this sd card as a template for setting up multiple RaspiBlitzes, click `Cancel` and run `/home/admin/XXprepareRelease.sh`. Once you see the LCD going white and the activity LED of the pi starts going dark, you can unplug power and remove the SD card. You have now built your own RaspiBlitz SD card image.

*Note: If you plan to use your self-build sd card as a MASTER copy and distribute it: Use a smaller 8GB card for that. This way it's ensured that it will fit on every 16 GB card recommended for RaspiBlitz later on.*

* [Can I run RaspiBlitz on other computers than RaspberryPi?](FAQ.md#can-i-run-raspiblitz-on-other-computers-than-raspberrypi)
* [How can I build an SD card other than the master branch?](FAQ.md#how-can-i-build-an-sd-card-other-then-the-master-branch)
* [How can I build an SD card from my forked GitHub Repo?](FAQ.md#how-can-i-build-an-sd-card-from-my-forked-github-repo)
