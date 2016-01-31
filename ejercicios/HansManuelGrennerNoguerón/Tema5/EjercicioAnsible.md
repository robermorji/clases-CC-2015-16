**Instala Ansible en tu sistema**

Ansible usa una serie de módulos de python que necesitan ser instalados previamente para su [correcto funcionamiento](http://docs.ansible.com/ansible/intro_installation.html#getting-ansible). Usando el gestor de paquetes para python :

```sudo pip install paramiko PyYAML Jinja2 httplib2 six ansible```


**Configura el fichero de inventarios de las IPs de dos máquinas**

Mediante ifconfig podemos obtener las IP's de ambas máquinas. Procedemos a añadirlo al fichero de hosts y asignárlo a la variable de entorno de ANSIBLE_HOSTS.


```echo "<IP's>" >> ./ansible_hosts
export ANSIBLE_HOSTS = ./ansible_hosts```



