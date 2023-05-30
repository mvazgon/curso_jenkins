pipeline{
    agent any
    stages{
        stage("Saludo."){
            steps{
                echo "Hola Mundo"
            }
        }
        stage("Lee el archivo que se indica hardcodeado"){
          steps{
            script{
              def archivo=readFile("Bienvenida.txt")
              println archivo
            }
          }
        }
    }
}
