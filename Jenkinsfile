properties([
    parameters([
        booleanParam(name: 'failBuild', defaultValue: false, description: 'fail the build for testing'),
        booleanParam(name: 'unstableBuild', defaultValue: false, description: 'mark the build as unstable')
    ])
])

node('master') {
    stage ('Build') {
        checkout scm
        println('Building it!!!')
        sleep(5)
        if (params.failBuild) {
            error('Got an error building.')
        }
        if (params.unstableBuild) {
            currentBuild.result = hudson.model.Result.UNSTABLE.toString()
        }
    }
    stage ('Step2') {
        println('Step2ing it!!!')
        sleep(5)
    }
    stage ('Publish') {
        println('Publishing it!!!')
        sleep(5)
    }
}
