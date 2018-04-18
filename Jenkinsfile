pipeline {
  agent any
  stages{
    stage("build harmony") {
      steps {
        data=readFile('./builddata')
        echo "${data}"
        retry(3) {
            build(
                    job: "Build_Worker",
                    parameters: [
                            [$class: 'StringParameterValue', name: 'AppType', value: 'CS'],
                            [$class: 'StringParameterValue', name: 'QAEnv', value: 'e2e']
                    ]
            )
        }
      }
    }
  }
}
