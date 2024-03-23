@Library('mylibrary')_
node('built-in')
{
    stage('ContDownload')
    {
        cicd.gitDownload("maven")
    }
    stage('ContBuild')
    {
        cicd.mavenBuild()

    }
    stage('ContDeployment')
    {
         cicd.tomcatDeploy("ScriptedPipelinewithSharedLibraries","172.31.17.128","testapp")

    }
    stage('ContTesting')
    {
        cicd.gitDownload("functionaltesting")
        
    }
    stage('testcases')
    {
        cicd.runSelenium("ScriptedPipelinewithSharedLibraries")

    }
    stage('ContDelivery')
    {
         cicd.tomcatDeploy("ScriptedPipelinewithSharedLibraries","172.31.22.117","prodapp")
    }
}



