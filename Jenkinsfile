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
    stages{
        stage("Saludo."){
            steps{
                echo "Hola Mundo"
            }
        }
        stage("Dia de la semana"){
            steps{
                script{
                    def dia=new Date().getDay()
                    def map=[1:"lunes",2:"Martes",3:"Miércoles",4:"Jueves",5:"Viernes",6:"Sabado",7:"Domingo"]
                    println dia
                    println map
                    if(dia==2){
                        userEnv=User.current()
                        println "El usuarios es:"+userEnv
                    }else if(dia==3){
                        fecha = new Date().getDateTimeString()
                        println "Es "+map[dia]+" el tiempo que hace es: "+fecha
                    }else if(dia==4){
                        println "Es "+map[dia]+" clonar repo"
                        git branch: "main" , url: "https://github.com/mvazgon/curso_jenkins.git"
                        sh """
                            ls -lrtha
                        """
                    }else{
                        println "Es cualquier otro dia, no se hace nada"
                    }
                }
            }
        }
    }       
}
