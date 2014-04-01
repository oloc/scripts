# 
# OLOC - 01/12/13

Apt=/etc/apt
Firmware=firmware-iwlwifi
Module=iwl3945

echo "Conversion of the sources.list from main to contrib non-free"
cp ${Apt}/sources.list ${Apt}/sources.main
sed 's/main/main contrib non-free/g' < ${Apt}/sources.list > ${Apt}/sources.contrib.non-free
cp ${Apt}/sources.contrib.non-free ${Apt}/sources.list

echo "Installation of ${Firmware} in progress..."
aptitude update && aptitude install ${Firmware}
echo "Installation of ${Firmware} done."

echo "Reload of the module ${Module}"
modprobe -r ${Module}
modprobe ${Module}

echo "Last aptitude update with main:"
cp ${Apt}/sources.main ${Apt}/sources.list
aptitude update
