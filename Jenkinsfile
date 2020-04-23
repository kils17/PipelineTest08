pipeline {
    agent any
    stages {
        stage('get current date') {
            steps {
                // readJSON이라는 내장함수를 사용하기 위해 script를 선언했습니다.
                script {
                    // sh 로 curl 명령어를 실행하여 JSON_URL 에서 JSON 데이터를 요청하여 date.json에 저장합니다
                    sh "curl -f -o date.json ${JSON_URL}"
                    // date.json 의 데이터를 읽어 json에 저장합니다.
                    json = readJSON file: 'date.json'
                    // 데이터를 출력합니다.
                    echo "${json.date}"
                }
            }
        }
    }
}
