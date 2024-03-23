@Library('mylibrary')_
node('built-in')
{
    stage('ContDownload_master')
    {
        cicd.gitDownload("maven")
    }
    stage('ContBuild_master')
    {
        cicd.mavenBuild()

    }
    stage('ContDeployment_master')
    {
         cicd.tomcatDeploy("ScriptedPipelinewithSharedLibraries","172.31.17.128","testapp")

    }
    stage('ContTesting_master')
    {
        cicd.gitDownload("functionaltesting")
        
    }
    stage('testcases_master')
    {
        cicd.runSelenium("ScriptedPipelinewithSharedLibraries")

    }
    stage('ContDelivery_master')
    {
         cicd.tomcatDeploy("ScriptedPipelinewithSharedLibraries","172.31.22.117","prodapp")
    }
}



