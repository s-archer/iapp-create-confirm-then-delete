node {
    stage('Starting') {
       //Create an iApp on the BIG-IP
    }
    stage('iApp-Deployment') {
        //Creating the iApp with a REST call
       build 'REST-iApp-Create'
       //chatops slack message that run has completed
       slackSend(
          channel: '#openshift',
          color: 'good',
          message: 'CREATED!  Jenkins file has been downloaded from git.  The iApp has been deployed to the F5 BIG-IP.',
          teamDomain: 'archer-demo',
          token: 'TEiSXYIrpraW3INc3irxvJL7'
          )
    }
    stage('Approval') {
       //Gate the process and require approval
       input 'Can the iApp be deleted?'
       //chatops slack message that run has completed
       slackSend(
           channel: '#openshift',
           color: 'good',
           message: 'APPROVED!  The deletion of the iApp deployed onto F5 BIG-IP has been approved.',
           teamDomain: 'archer_demo',
           token: 'TEiSXYIrpraW3INc3irxvJL7'
           )
    }
    stage('iApp-Removal') {
        //Following approval, the iApp will be deleted.
       build 'REST-iApp-Delete'
       //chatops slack message that run has completed
       slackSend(
          channel: '#openshift',
          color: 'good',
          message: 'DELETED!  The iApp has been deleted from the F5 BIG-IP.',
          teamDomain: 'archer_demo',
          token: 'TEiSXYIrpraW3INc3irxvJL7'
          )
    }
 }
