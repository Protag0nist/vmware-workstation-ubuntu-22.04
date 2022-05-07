# Refresher Notes on How To Install VMware's Workstation Pro 16 on Ubuntu 22.04
1. Download the .bundle from VMware's website - https://www.vmware.com/uk/products/workstation-pro/workstation-pro-evaluation.html
2. Set execute perms - sudo chmod +x VMware-Workstation-Full-16.xxxxxx.bundle
3. Install dependancies - sudo apt update && sudo apt install build-essential make gcc -y
4. Run bundle file - sudo ./VMware-Workstation-Full-16.xxxxxx.bundle
5. Run Workstation from Applications menu.
6. Install required modules.
7. If encountering error when compiling for interfaces (vmmon, vmnet), run the following with corresponding number with downloaded version:

wget https://github.com/mkubecek/vmware-host-modules/archive/workstation-16.2.3.tar.gz
tar -xzf workstation-16.2.3.tar.gz 
ls
cd vmware-host-modules-workstation-16.2.3/
tar -cf vmmon.tar vmmon-only
tar -cf vmnet.tar vmnet-only
sudo cp -v vmmon.tar vmnet.tar /usr/lib/vmware/modules/source/
cd ..
sudo vmware-modconfig --console --install-all
