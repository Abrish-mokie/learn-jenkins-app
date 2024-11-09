// pipeline {
//     agent any

//     stages {
//         stage('w/o docker'){
//             steps{
//                 sh '''
//                 echo "Withough docker"
//                 ls -la
//                 touch container-no.txt
//                 ls -la
//                 pwd
//                 '''
//             }
//         }
//         stage('w/ docker') {
//             agent{
//                 docker{
//                     image 'node:18-alpine'
//                     reuseNode true
//                 }
//             }
//             steps {
//                 sh '''
//                 echo "With docker"
//                 ls -la
//                 touch container-yes.txt
//                 ls -la
//                 pwd
//                 '''
//             }
//         }
//     }
// }
pipeline {
    agent any

    stages {
        stage('Build'){
            agent{
                docker{
                    image 'node:18-alpine'
                    reuseNode true
                 }
            }
            steps {
                 sh '''
                 ls -la
                 node --version
                 npm --version
                 npm ci
                 npm run build
                 ls -la
              '''
        }
    }
}
