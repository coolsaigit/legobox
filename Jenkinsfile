import groovy.json.*
  
node ('master'){
 
    stage 'Create a VPC'
        def vpcJob = build job: 'vpc', parameters: [
            string(name: 'stage', value: "${stage}"),
        ]

    stage 'Create a Key'
        def keyJob = build job: 'key', parameters: [
            string(name: 'stage', value: "${stage}"),
        ]
}

@NonCPS
def getJsonData(String json) {
   def jsonSlurper = new JsonSlurperClassic()
   def resultJson = jsonSlurper.parseText(json)
   def m = [:]
   m.putAll(resultJson)
   return m
}
