!/bin/bash

dominio="DC=rsai-tipy-uy,DC=duckdns,DC=org"

#sudo samba-tool ou create "OU=Usuarios,$dominio"
sudo samba-tool ou create "OU=Empleados,OU=Usuarios,$dominio"
sudo samba-tool ou create "OU=Proveedores,OU=Usuarios,$dominio"
sudo samba-tool ou create "OU=Ex-Empleados,OU=Usuarios,$dominio"
sudo samba-tool ou create "OU=RRHH,OU=Empleados,OU=Usuarios,$dominio"
sudo samba-tool ou create "OU=Sistemas,OU=Empleados,OU=Usuarios,$dominio"
sudo samba-tool ou create "OU=Sysadmins,OU=Sistemas,OU=Empleados,OU=Usuarios,$dominio"
sudo samba-tool ou create "OU=Devs,OU=Sistemas,OU=Empleados,OU=Usuarios,$dominio"

#sudo samba-tool ou create "OU=Equipos,$dominio"
sudo samba-tool ou create "OU=Desktops,OU=Equipos,$dominio"
sudo samba-tool ou create "OU=Servers,OU=Equipos,$dominio"

#sudo samba-tool ou create "OU=ServiceAccounts,$dominio"

#sudo samba-tool ou create "OU=Grupos,$dominio"
sudo samba-tool ou create "OU=Grupos_de_Seguridad,OU=Grupos,$dominio"
sudo samba-tool ou create "OU=Grupos_Distribuidos,OU=Grupos,$dominio"

echo "Unidades Organizacionales creadas correctamente."
