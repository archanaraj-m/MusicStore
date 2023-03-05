node('MAVEN_JDK8')
{
    stage('vcs')
    {
        git 'https://github.com/CICDProjects/MusicStore.git'
    }
    stage('restore')
    {
        sh 'dotnet restore ./MusicStore/MusicStore.csproj'
    }
    stage('build')
    {
        sh 'dotnet build ./MusicStore/MusicStore.csproj'
    }
    stage ('test')
    {
        sh 'dotnet test ./MusicStoreTest/MusicStoreTest.csproj --logger:"junit;LogFileName=test-results.xml"'
    }
}

