pipeline {
    agent {
        docker {
            // 下载maven
            image 'maven:3-alpine' 
            // 挂载本地镜像仓库
            args '-v /root/.m2:/root/.m2' 
        }
    }
    stages {
        stage('Build') { 
            steps {
                // sh 'mvn -B -DskipTests clean package' 
                sh 'mvn -B -gs maven-setting.xml -DskipTests clean package' 
                sh 'echo 这是一次修改，触发远程构建'
            }
        }
    }
}
