# Project
  steps{
                  echo 'compiling..'
                  bat 'mvn compile'
                  sh 'mvn compile'
	      }
          }
          stage('CodeReview'){

              steps{

		  echo 'codeReview'
                  bat 'mvn pmd:pmd'
                  sh 'mvn pmd:pmd'
              }
          }
           stage('UnitTest'){

              steps{

                  bat 'mvn test'
                  sh 'mvn test'
              }
               post {
               success {
@@ -41,7 +41,7 @@ pipeline{

              steps{

                  bat 'mvn package'
                  sh 'mvn package'
              }
          }
