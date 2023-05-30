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
                def dia=new Date().getDay()
                def map=[1:"lunes",2:"Martes",3:"Miércoles",4:"Jueves",5:"Viernes",6:"Sabado",7:"Domingo"]
                def fecha = new Date().getDateTimeString()
                script{
                    println dia
                    println map
                    if(dia==2){
                        println "El usuarios es:"+env.USER
                    }else if(dia==3){
                
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
        stage("Recopilacion de variables")
        {
            steps{
                println dia + " " +map[dia]+" "+fecha
            }
        }
    }       
}
