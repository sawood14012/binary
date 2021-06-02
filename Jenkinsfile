pipeline {
    agent {
        label 'master'
    }
   stages {
        stage ('test-go') {
            steps {
                echo pwd()
                sh 'which go'
                sh 'go version'
                echo "running crda analysis"
                crdaAnalysis cliVersion: '', crdaKeyId: '3f33291d-1dd1-4163-9b7e-c8038f3a9a29', file: '/var/lib/jenkins/jobs/plugin-pipeine-test/workspace/go.mod'
                echo "finished"
            }
        }
        stage ('test-mvn') {
            steps {
                echo pwd()
                sh 'which mvn'
                sh 'mvn --version'
                echo "running crda analysis"
                crdaAnalysis cliVersion: '', crdaKeyId: '3f33291d-1dd1-4163-9b7e-c8038f3a9a29', file: '/var/lib/jenkins/jobs/plugin-pipeine-test/workspace/acceptance-tests/manifests/pom.xml'
                echo "finished"
            }
        }
        stage ('test-python') {
            steps {
                echo pwd()
                sh 'which python'
                sh 'python -V'
                sh 'cd /var/lib/jenkins/jobs/plugin-pipeine-test/workspace/acceptance-tests/manifests && pip3 install --user -r requirements.txt'
                echo "running crda analysis"
                crdaAnalysis cliVersion: '', crdaKeyId: '3f33291d-1dd1-4163-9b7e-c8038f3a9a29', file: '/var/lib/jenkins/jobs/plugin-pipeine-test/workspace/acceptance-tests/manifests/requirements.txt'
                echo "finished"
            }
        }
        stage ('test-npm') {
            steps {
              nodejs('nodejs') {
                echo pwd()
                sh 'which node'
                sh 'node --version'
                sh 'cd /var/lib/jenkins/jobs/plugin-pipeine-test/workspace/acceptance-tests/manifests && npm install'
                echo "running crda analysis"
                crdaAnalysis cliVersion: '', crdaKeyId: '3f33291d-1dd1-4163-9b7e-c8038f3a9a29', file: '/var/lib/jenkins/jobs/plugin-pipeine-test/workspace/acceptance-tests/manifests/package.json'
                echo "finished"
                }
            }
        }
    }
}
