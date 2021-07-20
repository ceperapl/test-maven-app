@Library('piper-lib-os') _

node() {
    stage('prepare') {
	    deleteDir()
        checkout scm
        setupCommonPipelineEnvironment script:this
    }
    stage('build') {
        sonarExecuteScan script: this
        // kanikoExecute script: this
    }
    influxWriteData script: this
}
