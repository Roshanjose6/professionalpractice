pipeline {
agent any
stages {
stage("Build") {
steps {
echo "Initiating build process"
}
}
stage("Unit and Integration Tests") {
steps {
echo "Executing unit tests using JUnit"
echo "Performing integration tests with Postman"
}
post {
success {
emailext attachLog: true,
subject: "Tests completed successfully",
body: "Both unit and integration tests have been successfully executed.",
to: "roshanjoseapr6@gmail.com"
}
failure {
emailext attachLog: true,
subject: "Test failures detected",
body: "One or more tests have failed during execution.",
to: "roshanjoseapr6@gmail.com"
}
}
}
stage("Code Analysis") {
steps {
echo "Conducting code analysis with SonarQube"
}
}
stage("Security Scan") {
steps {
echo "Conducting security scan using OWASP ZAP"
}
post {
success {
emailext attachLog: true,
subject: "Security scan completed successfully",
body: "Security scan has been successfully completed.",
to: "roshanjoseapr6@gmail.com"
}
failure {
emailext attachLog: true,
subject: "Security scan failed",
body: "The security scan has failed. Immediate attention required.",
to: "roshanjoseapr6@gmail.com"
}
}
}
stage("Deploy to Staging") {
steps {
echo "Deploying to Staging environment using Kubernetes"
}
}
stage("Integration Tests on Staging") {
steps {
echo "Executing integration tests on Staging environment"
}
}
stage("Deploy to Production") {
steps {
echo "Deploying to Production environment using Kubernetes"
}
}
}
post {
success {
emailext attachLog: true,
subject: "Pipeline execution successful",
body: "The pipeline has been executed successfully!",
to: "roshanjoseapr6@gmail.com"
}
failure {
emailext attachLog: true,
subject: "Pipeline execution failed",
body: "The pipeline execution has failed. Immediate investigation required.",
to: "roshanjoseapr6@gmail.com"
}
}
}
