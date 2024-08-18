pipeline
{
    agent
    {
        node
        {
            label 'JenkinsSlaveNodeLabel'
        }
    }
    stages
    {
        stage("Checkout code stage")
        {
            steps
            {
                git url:'https://github.com/devopsak1/jenkinsrepo_1.git',branch:'main'
            }
        }
        stage("cleanup stage")
        {
            steps
            {
                sh 'docker rm -f $(docker ps -aq)'
                sh 'docker rmi -f myimage'
            }
        }
        stage("Docker build image")
        {
            steps
            {
                sh 'bocker build -t myimage .'
            }
        }
        stage("create container")
        {
            steps
            {
                sh 'docker run -d -p 8501:8501 myimage'
            }
        }
    }
}