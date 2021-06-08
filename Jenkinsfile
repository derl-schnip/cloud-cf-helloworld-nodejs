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
      pushToCloudFoundry(
        target: 'https://api.cf.eu10.hana.ondemand.com',
        organization: '91ed8854trial_org',
        cloudSpace: 'dev',
        credentialsId: 'CF_CREDENTIALSID'
        )
    }
}
