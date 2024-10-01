\\
#1. Descargar e comprobar que una imaxe está no teu equipo

#Para descargar una imaxe de docker usase o comando: docker pull imaxe
#Para comprobalo: docker images

docker pull ubuntu
docker images
#2. Crear un contenedor sen nome, queda arrincado?, cómo obtés o nome?

#Con "docker run imaxe" crease contenedor sen  nome e con docker "ps -a" podense ver todos os contenedores (ID,imaxe,command,created,status,ports,names)
#Por defecto non queda arrincado, pero escribindo o parámetro "-it" queda arrincado

docker run (-it) ubuntu
docker ps -a

#3. Crea un contenedor co nome 'u1', cómo accedes a el?

#Para indicarlle un nome usase o parámetro "--name"
#Para acceder aos seus contidos podese facer desde visual studio code

docker run --name u1 ubuntu

#4. Comproba a súa ip e fai ping a google.com

#Con "docker inspect nomecontenedor" podese ver a direccion ip, pero como este está usando a direccion ip do host, este mostrase en branco
#Co comando ping comprobase a conectividade

docker inspect u1
ping google.com

#5. Crea un contenedor coo nome 'bono', pódese facer ping entre os contenedores?

#Con "docker run --name nome nomeimaxe crease un contenedor con ese nome
#Como todos os contenedores estan usando a dirección ip do host, non se pode facer "ping" entre eles.

docker run --name bono ubuntu

#6. Se pechas as terminales, qué pasa coo contenedor?

#Neste caso nada porque ningunha estabase usando porque non se crearon co parámetro "-it". 

#7. Cánta memoria no disco duro ocupaches? Usa docker para calculalo.

#Con docker "system df" mirase o uso de espazo de imaxes, contenedores, volumenes e caché.

docker system df

#8. Canta RAM ocupan os contenedores? Crea varios para ocupalos.

#Primeiro creo varios contenedores con "docker run -it imaxe" usando a imaxe de ubuntu.
#Despois con "docker stats" miro o consumo da ram.
#Para mandalos a segundo plano uso &

docker run -it ubuntu &
docker run -it ubuntu &
docker stats

#9. Como fixeches para clonar o repositorio?

#Con "git clone https://dirrepositorio.git" clonase o repositorio creando una carpeta en la ruta actual.

git clone https://github.com/anxovaz/p1comandosdocker_anxo.git

#10. Cómo engades o arquivo readme2.md

#Con touch creo el archivo.

touch readme2.md

#11. Os pasos a seguir para subir o arquivo que estás editando e o arquico readme2.md

git init
git add ruta archivo #Para agregar archivos
git commit -m nomecommit #Adjuntar los archivos
git push https://github.com/anxovaz/p1comandosdocker_anxo.git #Subirlos al repositorio indicado


#12. Cómo comprobarías que existen diferencias entre o teu repositorio local e o remote?

git status




\\
