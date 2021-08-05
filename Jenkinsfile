node('MASTER') {
    stage('scm') {
        git 'https://github.com/dileep208/openmrs-core.git'
    }
    stage('build') {
        sh 'mvn package'
    }
    stage('post build') {
        junit '**/TEST-*.xml'
        archive '**/*.war'
        emailext body: '', subject: 'This build is sucessful', to: 'ugra.deep@gmail.com'
    }

}