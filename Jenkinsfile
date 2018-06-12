node {
   def mvnHome
   stage('Preparation') { // for display purposes
      git 'https://github.com/CodeMines/SampleMavenProject.git'           
      mvnHome = tool 'M3'
   }
   stage('build java') {
      // Run the maven build
      if (isUnix()) {
         sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore clean package"
      } else {
         bat(/"${mvnHome}\bin\mvn" clean install/)
      }
   }
}