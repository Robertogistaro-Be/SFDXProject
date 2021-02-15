#!groovy
import groovy.json.JsonSlurperClassic
node {


 
	    println 'CHECK '+isUnix()
        stage('Deploye Code') {
            if (isUnix()) {
                rc = sh returnStatus: true, script: "${toolbelt} force:auth:jwt:grant --clientid ${CONNECTED_APP_CONSUMER_KEY} --username ${HUB_ORG} --jwtkeyfile ${jwt_key_file} --setdefaultdevhubusername --instanceurl ${SFDC_HOST}"
            }else{
                 rc = bat returnStatus: true, script: "sfdx force:auth:jwt:grant --clientid 3MVG9SOw8KERNN084rzxiYMlQEepqdGpgFyuG9hr_IOJB5N3Cr6qnLC__WqiNFmIsJblNRTB2.Hb6gXGnGPtX --jwtkeyfile server.key --username robertogistaro@besolutions.it --instanceurl https://login.salesforce.com --setdefaultdevhubusername"
            }
            if (rc != 0) { error 'hub org authorization failed' }

		
        
    }
}
