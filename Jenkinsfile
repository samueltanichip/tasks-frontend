pipeline {
    agent any // Executa em qualquer agente disponível

    tools {
        maven 'M3' // Define a versão do Maven configurada no Jenkins
        jdk 'JDK11' // Define a versão do JDK configurada no Jenkins
    }

    stages {
        // Etapa de compilação
        stage('Build') {
            steps {
                echo 'Compilando o projeto Java com Maven...'
                sh 'mvn clean compile' // Compila o código-fonte
            }
        }

        // Etapa de execução de testes
        stage('Test') {
            steps {
                echo 'Executando testes...'
                sh 'mvn test' // Executa os testes unitários
            }
        }

        // Etapa de empacotamento
        stage('Package') {
            steps {
                echo 'Empacotando o projeto...'
                sh 'mvn package' // Gera o arquivo JAR
            }
        }

        // Etapa opcional para deploy (exemplo simples)
        stage('Deploy') {
            steps {
                echo 'Realizando deploy...'
                // Aqui você pode adicionar comandos para enviar o JAR para um servidor, por exemplo
                sh 'echo "Deploy realizado com sucesso!"'
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
