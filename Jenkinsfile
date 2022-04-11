podTemplate(containers: [
    containerTemplate(
        name: 'maven', 
        image: 'maven:3.8.1-jdk-8', 
        command: 'sleep', 
        args: '30d'
        )
  ]) {

    node(POD_LABEL) {
        stage('Get a Maven project') {
            container('maven') {
                stage('Build') {
                    steps {
                        sh'''
                            ls
                            pwd
                            mvn -B -DskipTests clean package
                        '''
                    }
                }
            }
        }

    }
}