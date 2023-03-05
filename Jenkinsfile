node('MAVEN_JDK8')
{
    stage('vcs')
    {
        git url: 'https://github.com/CICDProjects/MusicStore.git',
            branch: 'main'
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
    stage('clientapp')
    {
        sh 'cd ./MusicStore/ClientApp'
    }
    stage('installnpm')
    {
        sh 'npm install'
    }
    stage('runbuild')
    {
        sh 'npm run build'
    }
    stage('test')
    {
        sh 'npm run test'
    }
}
