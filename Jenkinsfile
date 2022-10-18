node("OPEN-JDK8") {
    stage("vcs") {
      git branch: 'master', url: 'https://github.com/instinct1one/game-of-life.git'
    }
    stage("build") {
        sh 'mvn package'
    }
    stage("archive results") {
        junit '**/surefire-reports/*.xml'
    }
    stage("clean") {
        cleanWs cleanWhenAborted: false, cleanWhenFailure: false, cleanWhenNotBuilt: false, cleanWhenUnstable: false
    }
}
