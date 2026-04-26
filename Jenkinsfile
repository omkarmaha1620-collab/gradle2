pipeline {
agent any

```
environment {
    JAVA_HOME = '/usr/lib/jvm/java-21-openjdk-amd64'
    PATH = "${JAVA_HOME}/bin:${env.PATH}"
}

stages {

    stage('Checkout') {
        steps {
            // Jenkins automatically checks out repo
            echo "Code checkout completed"
        }
    }

    stage('Build') {
        steps {
            sh 'chmod +x gradlew'
            sh './gradlew build'
        }
    }

    stage('Test') {
        steps {
            sh './gradlew test'
        }
    }

    stage('Run Application') {
        steps {
            sh './gradlew run'
        }
    }
}

post {
    success {
        echo "✅ Build Successful"
    }
    failure {
        echo "❌ Build Failed"
    }
}
```

}
