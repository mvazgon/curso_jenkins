# curso_jenkins

Creamos la clave publica en el usuario que ejecuta jenkins en la máquina remota, con el comando:
 ssh-keygen -t rsa -b 4096 -C "direccion_email@cuenta_github.com"
 
Se copia la clave pública a github

Se dá de alta esa clave pública en github

Ya tenemos construida la confianza entre Github y nuestro servidore de automatización. 
