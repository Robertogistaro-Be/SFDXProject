#!groovy
import groovy.json.JsonSlurperClassic
node {
    def JWT_KEY_CRED_ID = env.JWT_CRED_ID_DH

        
        withCredentials([file(credentialsId: JWT_KEY_CRED_ID, variable: 'server_key_file')]) {

            // -------------------------------------------------------------------------
            // Authorize the Dev Hub org with JWT key and give it an alias.
            // -------------------------------------------------------------------------

            stage('Authorize DevHub') {
                rc = command "${toolbelt}/sfdx auth:jwt:grant --instanceurl https://login.salesforce.com --clientid 3MVG9SOw8KERNN084rzxiYMlQEepqdGpgFyuG9hr_IOJB5N3Cr6qnLC__WqiNFmIsJblNRTB2.Hb6gXGnGPtX --username robertogistaro@besolutions.it --jwtkeyfile ${server_key_file} --setdefaultdevhubusername --setalias HubOrg"
                if (rc != 0) {
                    error 'Salesforce dev hub org authorization failed.'
			println error
                }
		println rc    
            }
 
	  
        
    }
}
