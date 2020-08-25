properties([
    parameters([
        booleanParam(name: 'uploadBuild', defaultValue: false, description: 'upload the build to velocity'),
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
    stage ('Upload Build') {
        if (params.uploadBuild) {
           step([
                $class: 'UploadBuild',
                debug: true,
                fatal: false,
                id: "${currentBuild.displayName}",
                name: "${currentBuild.displayName}",
                appName: 'test2',
                startTime: "${currentBuild.startTimeInMillis}",
                endTime: "${System.currentTimeMillis()}",
                requestor: "Jenkins",
                revision: "crap",
                status: "success",
                tenantId: "5ade13625558f2c6688d15ce",
                versionName: "${currentBuild.displayName}"
            ])
        }
    }
}
