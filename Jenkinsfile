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
        stage("Docker build image")
        {
            steps
            {
                sh 'docker build -t myimage .'
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