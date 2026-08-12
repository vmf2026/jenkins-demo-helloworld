pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Descargando el código desde el repositorio...'
                checkout scm
            }
        }

        stage('Compilar') {
            steps {
                echo 'Compilando HelloWorld.java con javac...'
                sh 'javac -d out src/HelloWorld.java'
            }
        }

        stage('Ejecutar') {
            steps {
                echo 'Ejecutando el programa...'
                sh 'java -cp out HelloWorld'
            }
        }
    }

    post {
        success {
            echo '✅ ¡El pipeline ha compilado y ejecutado el programa correctamente!'
        }
        failure {
            echo '❌ Algo ha fallado. Revisa el Console Output de la fase correspondiente.'
        }
    }
}
