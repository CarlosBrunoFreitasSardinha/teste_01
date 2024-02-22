pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                // Passo para obter o código-fonte do repositório Git
                //git branch: 'teste', url: 'https://github.com/CarlosBrunoFreitasSardinha/teste_01.git'
                echo 'Pipeline executada com sucesso!   ---- TESTE'

            }
        }        
        stage('Testes') {
            //steps {
                // Passo para executar os testes de unidade
                //sh 'dotnet test --logger:trx'
                // Publicar resultados dos testes para o Jenkins
                //junit '**/TestResult.xml'
            //}
        }
        
        stage('Construir Imagem Docker') {
            steps {
                // Construir a imagem Docker da aplicação
                script{
                        dockerapp = dpcker.build("CarlosBrunoFreitasSardinha/teste_01", '-f ./src/DockerFile ./src')
                        }
            }
        }
        
        stage('Implantação') {
            //steps {
                // Subir a aplicação utilizando Docker Compose
                //sh 'docker-compose up -d'
            //}
        }
    }
    
        post {
            success {
                // Ações a serem executadas em caso de sucesso (opcional)
                echo 'Pipeline executada com sucesso!'
            }
            failure {
                // Ações a serem executadas em caso de falha (opcional)
                echo 'A pipeline falhou!'
            }
        }
}