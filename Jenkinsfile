 @Library('github.com/pradeepitm12/osio-pipeline@staging') _

 osio {

 config runtime: 'go'
  ci {

            def resources = processTemplate(params: [
            release_version: "1.0.${env.BUILD_NUMBER}"
            ])
            build resources: resources
   }
   cd {

    def resources = processTemplate(params: [
    release_version: "1.0.${env.BUILD_NUMBER}"
              ])

               build resources: resources
               deploy resources: resources, env: 'stage'
               deploy resources: resources, env: 'run', approval: 'manual'
   }
   }