# COPRs of Interest

## "COPRs? What are these?"

There are times where packages you want won't be shipped by default in Fedora repos, things like niche software or bleeding-edge / development version of certain software. It allows developers to package their own software "off-band" to be distributed. They are analgous to [PPAs](https://launchpad.net/ubuntu/+ppas) in the Ubuntu / Debian world.

Further reading: [COPR FAQ](https://docs.copr.fedorainfracloud.org/user_documentation.html#faq)

## "OK, how do I use these COPRs?"

You enable them then install whatever package you need from them, example:

```
sudo dnf enable swayfx/swayfx

sudo dnf install -y swayfx
```

## List
- [swayfx/swayfx](https://copr.fedorainfracloud.org/coprs/swayfx/swayfx/): For the [Sway fork](https://github.com/WillPower3309/swayfx)
- [faugus/faugus-launcher](https://github.com/Faugus/faugus-launcher): Game launcher. Also available as a [flatpak](https://flathub.org/en/apps/io.github.Faugus.faugus-launcher)
- [solopasha/hyprland](https://copr.fedorainfracloud.org/coprs/solopasha/hyprland): All things hyprland you could possibly need.
- [avengemedia/dms](https://copr.fedorainfracloud.org/coprs/avengemedia/dms/): Dank Material Shell, stable branch
- [avengemedia/dms-git](https://copr.fedorainfracloud.org/coprs/avengemedia/dms-git/): Dank Material Shell, Development branch
- [codifryed/CoolerControl](https://copr.fedorainfracloud.org/coprs/codifryed/CoolerControl/): For [CoolerControl](https://docs.coolercontrol.org/)

