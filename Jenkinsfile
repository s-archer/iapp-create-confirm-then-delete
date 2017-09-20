node {
    stage('Starting') {
       //Create an iApp on the BIG-IP
    }
    stage('iApp-Deployment') {
        //Creating the iApp with a REST call
       build 'REST-iApp-Create'
       //chatops slack message that run has completed
       slackSend(
          channel: '#jenkins_builds',
          color: 'good',
          message: 'Super-NetOps Engineer is about to deploy an F5 Service Framework, Approval Needed!',
          teamDomain: 'f5agilitydevops',
          token: 'vLMQmBq2tiyiCcZoNlbmAi0Z'
          )
    }
    stage('Approval') {
       //Gate the process and require approval
       input 'Can the iApp be deleted?'
       //chatops slack message that run has completed
       slackSend(
           channel: '#jenkins_builds',
           color: 'good',
           message: 'Super-NetOps Engineer just approved a new F5 Service Framework, thats some serious Continuous Delivery!',
           teamDomain: 'f5agilitydevops',
           token: 'vLMQmBq2tiyiCcZoNlbmAi0Z'
           )
    }
    stage('iApp-Removal') {
        //Following approval, the iApp will be deleted.
       build 'REST-iApp-Delete'
       //chatops slack message that run has completed
       slackSend(
          channel: '#jenkins_builds',
          color: 'good',
          message: 'Super-NetOps Engineer just added a Node to a Service, Production is Online!',
          teamDomain: 'f5agilitydevops',
          token: 'vLMQmBq2tiyiCcZoNlbmAi0Z'
          )
    }
 }
