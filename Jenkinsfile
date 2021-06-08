@Library('piper-lib-os') _
node() {
    stage('prepare') {
        checkout scm
        setupCommonPipelineEnvironment script:this
    }
    stage('build') {
      bat 'mbt init'
      bat 'make -f Makefile.mta p=cf'
    }
}
