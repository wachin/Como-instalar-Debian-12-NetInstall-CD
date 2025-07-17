

Ahorita reinicio y si puedo entrar, como no instalé ninguna interfaz gráfica ni la de debian mismo entonces solo aparece una terminal (no hay ninguna interfaz gráfica). La terminal que aparece dice: 

```
Debian/Linux 12 netinst tty1`

netinst login: _
```

allí poner el nombre de usuario, y luego dice: 

password:

Ponga la contraseña de ese usuario y de Enter y aparece en mi caso: 

```
wachin@netinst:^$
```

ahora debemos escribir:

```
su
```

y poner la contraseña de superusuario (root) 

ahora me aparece así: 

```
root@netinst:/home/wachin#
```

y allí poner:

```
apt update
```
