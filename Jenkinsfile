pipeline {
    agent any
    stages {

  stage('Checkout:') {
        steps {
        checkout scm
}
}

stage('Build') {
steps {
       echo 'Checking ython application'
       bat 'python -m unittest app'
}
}

stage('Run application')
{
steps {
  bat 'python app.py'
}
}
}
