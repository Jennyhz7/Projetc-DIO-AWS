#!/bin/bash

echo "Criando usuários do sistema..."

useradd Carlos -c "Convidado" -s /bin/bash -m -p $(openssl passwd -crypt Senha123)
passwd Carlos -e

useradd Maria -c "Convidado" -s /bin/bash -m -p $(openssl passwd -crypt Senha123)
passwd Maria -e

useradd João -c "Convidado" -s /bin/bash -m -p $(openssl passwd -crypt Senha123)
passwd João -e

useradd Debora -c "Convidado" -s /bin/bash -m -p $(openssl passwd -crypt Senha123)
passwd Debora -e

useradd Sebastiana -c "Convidado" -s /bin/bash -m -p $(openssl passwd -crypt Senha123)
passwd Sebastiana -e

useradd Roberto -c "Convidado" -s /bin/bash -m -p $(openssl passwd -crypt Senha123)
passwd Roberto -e

useradd Josefina -c "Convidado" -s /bin/bash -m -p $(openssl passwd -crypt Senha123)
passwd Josefina -e

useradd Amanda -c "Convidado" -s /bin/bash -m -p $(openssl passwd -crypt Senha123)
passwd Amanda -e

useradd Rogerio -c "Convidado" -s /bin/bash -m -p $(openssl passwd -crypt Senha123)
passwd Rogerio -e

echo "Criação de usuários finalizado!!"


echo "Criando Grupos..."
groupadd GRP_ADM
groupadd GRP_VEN
groupadd GRP_SEC

echo "Grupos criados"

cat /etc/group


echo "Criado diretórios"

mkdir /home/Publico
mkdir /home/Adm
mkdir /home/Ven
mkdir /home/Sec

echo "Diretórios criados..."

ls -ll /home


echo "Alterando grupos"

usermod -G GRP_ADM Carlos
usermod -G GRP_ADM Maria
usermod -G GRP_ADM João

usermod -G GRP_VEN Debora
usermod -G GRP_VEN Sebastiana
usermod -G GRP_VEN Roberto

usermod -G GRP_SEC Josefina
usermod -G GRP_SEC Amanda
usermod -G GRP_SEC Rogerio

echo "Alteração de grupos realizada, usuários adicionados à seus grupos"

cat /etc/group

echo "Alteração de donos do diretórios"


chown root:GRP_VEN /home/Ven
chown root:GRP_ADM /home/Adm
chown root:GRP_SEC /home/Sec

echo "Donos dos grupos alterados"


echo "Alterando permissionamento"
chmod 777 /home/Publico
chmod 470 /home/Adm
chmod 470 /home/Ven
chmod 470 /home/Sec


echo "Permissões alteradas"
echo "Validando alterações"

ls -ll /home

echo "Projeto finalizado"

