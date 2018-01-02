node ('slave1'){
 gradle4 = tool 'gradle4'
 stage ('chekcout'){
    git url: 'https://github.com/lironsfadia/gradle-hello-world'
 }
 stage ('build')
 {
     sh "${gradle4}/bin/gradle clean jar"
 }
 stage('unit-test')
 {
     sh "${gradle4}/bin/gradle clean install"
     junit "test-results/junit-platform/*.xml"
 }
}
