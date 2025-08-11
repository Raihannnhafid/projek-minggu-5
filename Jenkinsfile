pipeline {
    agent any
 
    stages {
        stage('Run Test') {
            steps {
                bat "mvn test"
            }
 
            post {                
                // If Maven was able to run the tests, even if some of the test
                // failed, record the test results and archive the jar file.
                success {
                   publishHTML([
                       allowMissing: false, 
                       alwaysLinkToLastBuild: false, 
                       keepAll: false, 
                       reportDir: 'ExtentReports/LaporanPengujian/HtmlReport', 
                       reportFiles: 'ExtentHtml.html', 
                       reportName: 'Extent Report', 
                       reportTitles: '', 
                       useWrapperFileDirectly: true])
                }
            }
        }
    }
}
