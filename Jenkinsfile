properties([
    parameters([
        booleanParam(name: 'failBuild', defaultValue: false, description: 'fail the build for testing')
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
