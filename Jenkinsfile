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
    }
    stages{
        stage("Saludo."){
            steps{
                echo "Hola Mundo"
            }
        }
        stage("Dia de la semana"){
            steps{
                script{
                    def map=[1:"lunes",2:"Martes",3:"Miercoles",4:"Jueves",5:"Viernes",6:"Sabado",7:"Domingo"]
                    if(dia==2){
                        println dia
                        println "Los dias: ${dia}; el usuario es: ${env.USER}"
                    }else if(dia==3){
                        println dia
                        println "Es ${map[dia]} el tiempo que hace es: ${fecha}"
                    }else if(dia==4){
                        println dia
                        println "Es ${map[dia]}; y hay que clonar repo"
                        git branch: "main" , url: "https://github.com/mvazgon/curso_jenkins.git"
                        sh """
                            ls -lrtha
                        """
                    }else{
                        println dia
                        println "Es cualquier otro dia, no se hace nada"
                    }
                }                
            }
            
        }
        stage("Recopilacion de variables")
        {
            steps{
                script{
                    println dia + " "+fecha
                }
            }
        }
    }       
}
