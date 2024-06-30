#!/bin/bash

pipeline {
    agent any
    stages {
        stage('Example') {
            steps {
                script {
                    def containerId = sh(
                        script: 'docker ps --filter "status=running" --format "{{.ID}}"',
                        returnStdout: true
                    ).trim()
                    echo "Container ID: ${containerId}"
                }
            }
        }
    }
}

 if [ -n "$container_id" ]; then
 docker cp /var/lib/jenkins/workspace/2024-Q2/. "$container_id":/usr/share/nginx/html
 else
 docker build -t server /var/lib/jenkins/workspace/2024-Q2
 docker run -d -p 9090:80 server
 fi
