import java.text.SimpleDateFormat

pipeline {
    agent any
    environment {
        nombre_archivo = "Jenkinsfile.txt"
        mensajeUsuario = "Usuario: Anibal Salazar"
    }
    stages {
        stage("Bienvenid@") {
            steps {
                script {
                    def dia = new Date()
                    def formato = new SimpleDateFormat("dd/MM/yyyy")
                    def fechaFormato = formato.format(dia)
                    def saludo = "Bienvenid@ a la "
                    def ciudad = "Ciudad de Barcelona"
                    def fecha = "La fecha actual es: " + fechaFormato
                    def habitantes = "El numero de habitantes es: 1,62 millones"
                    def clima = "El clima actual es soleado"
                    env.bienvenida = saludo + "\n" + ciudad + "\n" + fecha + "\n" + habitantes + "\n" + clima
                    echo env.bienvenida
                }
            }
        }
        stage("Usuario") {
            steps {
                script {
                    echo env.BUILD_USER_ID
                }
            }
        }
        stage("Generación fichero proceso") {
            steps {
                script {
                    writeFile file: env.nombre_archivo, text: env.bienvenida + "\n" + env.mensajeUsuario
                    echo "Se ha generado el fichero: ${env.nombre_archivo}."
                }
            }
        }
    }
}
