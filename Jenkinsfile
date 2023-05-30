// EJERCICIO 3:
// Desarrollar un Jenkinsfile que informe el usuario ejecutando el PPL usando la variable de Environment USERNAME si el día es martes.
// Si el día es lunes no informar nada
// Si el día es miercoles informar el estado del tiempo actual
// Si el dia es jueves, clonar tu repositorio y la rama principal
// Si el día es viernes, no hacer nada.

// ENTREGABLES:
// Codigo de Jenkins
// Repositorio de Github.

pipeline{
    agent any
    environment{
        def dia=new Date().getDay()
        def fecha = new Date().getDateTimeString()
        def Mensaje=""
        def day=""
    }
    stages{
        stage("Saludo."){
            steps{
                echo "Hola Mundo"
            }
        }
        stage("Procesamos el dia de la semana"){
            steps{
                script{
                    def map=[1:"lunes",2:"Martes",3:"Miercoles",4:"Jueves",5:"Viernes",6:"Sabado",7:"Domingo"]
                    if(dia.toInteger()==2){
                        Mensaje="Los dias: ${map[dia]}; tenemos que saber que el usuario es: ${env.USER}"
                    }else if(diato.Integer()==3){
                        
                        Mensaje"Es ${map[dia]}, el tiempo que hace es: ${fecha}"
                    }else if(dia.toInteger()==4){
                        Mensaje="Es ${map[dia]}; y hay que clonar repo"
                        git branch: "main" , url: "https://github.com/mvazgon/curso_jenkins.git"
                        sh """
                            ls -lrtha
                        """
                    }else{
                        Mensaje="Es cualquier otro dia, no se hace nada"
                    }
                    println "Se ha calculado la acción en funcion de los dias."
                }                
            }
            
        }
        stage("Imprimimos lo que hacemos.")
        {
            steps{
                script{
                    println "${Mensaje}"
                }
            }
        }
    }       
}
