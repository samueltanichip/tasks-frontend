pipeline {
    agent any // Executa em qualquer agente disponível

    tools {
        maven 'Maven-3.8.8' // Nome da instalação do Maven configurada no Jenkins
        jdk 'JDK-21.0.6' // Nome da instalação do JDK configurada no Jenkins
    }

    stages {
        // Etapa de compilação
        stage('Build') {
            steps {
                echo 'Compilando o projeto Java com Maven...'
                bat 'mvn clean compile' // Compila o código-fonte
            }
        }

        // Etapa de execução de testes
        stage('Test') {
            steps {
                echo 'Executando testes...'
                bat 'mvn test' // Executa os testes unitários
            }
        }

        // Etapa de empacotamento
        stage('Package') {
            steps {
                echo 'Empacotando o projeto...'
                bat 'mvn package' // Gera o arquivo JAR
            }
        }

        // Etapa opcional para deploy (exemplo simples)
        stage('Deploy') {
            steps {
                echo 'Realizando deploy...'
                // Aqui você pode adicionar comandos para enviar o JAR para um servidor, por exemplo
                bat 'echo "Deploy realizado com sucesso!"'
            }
        }
    }

    // Pós-condições (opcional)
    post {
        success {
            echo 'Pipeline executado com sucesso!'
        }
        failure {
            echo 'Pipeline falhou. Verifique os logs para mais detalhes.'
        }
    }
}
