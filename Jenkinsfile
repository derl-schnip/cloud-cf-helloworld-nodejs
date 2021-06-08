@Library('piper-lib-os') _
node() {
    stage('prepare') {
        checkout scm
        setupCommonPipelineEnvironment script:this
    }
    stage('build') {
      bat 'mbt init'
      bat 'mbt build -p cf'
    }
    stage('deploy') {
      cloudFoundryDeploy script: this
    }
}
