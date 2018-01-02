node (‘slave1’){
 gradle4 = tool 'gradle4'
 stage ('chekcout'){
    git url: 'https://github.com/lironsfadia/gradle-hello-world', branch : ‘master’
 }
 stage ('build')
 {
     sh "${gradle4}/bin/gradle clean jar"
 }
 stage ('unit-test')
 {
     sh "${gradle4}/bin/gradle test"
     junit "build/test-results/junit-platform/*.xml"
 }
 stage ('func-test')
 {
     cmd_prefix = "test-data/int-test.sh build/libs/oto-gradle-1.0.jar"
     tests = ["one" : { sh "${cmd_prefix} otomato 'Hello Otomato!'"},
              "two" : { sh "${cmd_prefix} ''  'Hello Gradle!'"},
              "three" : { sh "${cmd_prefix} 'micrO'  'Hello Micro!'"}]
      parallel tests
 }

 }
