pipeline {
    agent any

    stages {
        stage('Fetch JSON from API') {
            steps {
                script {
                    def now = new Date()
                    def minute = now.format('mm', TimeZone.getTimeZone('Asia/Seoul')) as int
                    def next = (minute + 1) % 60
                    def apiUrl = "https://jsonplaceholder.typicode.com/todos/${next}"
                    echo "Fetching from: ${apiUrl}"

                    sh """
                    curl -s ${apiUrl} -o test.json
                    echo "Saved to test.json"
                    """
                }
            }
        }
    }
}
