node {
    stage([name: 'VCS Checkout']) {
        deleteDir()
        checkout scm
    }

    stage([name: "Releasing jar to nexus"]) {
        withCredentials([[$class          : 'UsernamePasswordMultiBinding',
                          credentialsId   : '5aa49a51-8b3e-48a2-b81d-f83253fd8d6f',
                          usernameVariable: 'NEXUS_USERNAME',
                          passwordVariable: 'NEXUS_PASSWORD']]) {
            sh 'lein release :patch'
        }
    }

}