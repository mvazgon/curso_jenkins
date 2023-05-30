pipeline{
    agent any
    stages{
        stage("Saludo."){
            steps{
                echo "Hola Mundo"
            }
        }
    
        stages("Dia de la semana"){
            script{
                def dia=new Date().getDay()
                def map=[1:"lunes",2:"Martes",3:"Miércoles",4:"Jueves",5:"Viernes",6:"Sabado",7:"Domingo"]
            }
        }
    }       
}
