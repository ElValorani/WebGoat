podTemplate(containers: [
    containerTemplate(name: 'maven', image:'maven:3.8.1-openjdk-15', command: 'sleep', args: '99d')
]) {
    node(POD_LABEL) {
        stage('stage') {
            git 'https://github.com/ElValorani/WebGoat.git'
            container('maven') {
                stage('build') {
                    sh 'mvn clean install'
                }
            }
        }
    }
}