@Library('piper-library-os') _

node()
{
stage('Prepare')

stage('Build')	      

            
    stage('DeployCommit') 
    gctsDeploy(
  script: this,
  host: 'https://hclutl1909.hcldigilabs.com:8001',
  abapCredentialsId: 'ABAPUserPasswordCredentialsId',
  repository: 'HCL_DevOps_V1',
  remoteRepositoryURL: 'https://github.com/HCL-Techno/HCL_DevOps_V1',
  role: 'TARGET',
  vSID: 'FEF',

	    )
	
stage('RunUnitTest') 
    gctsExecuteABAPUnitTests(
      script: this,
      host: 'https://hclutl1909.hcldigilabs.com:8001',
      client: '200',
      abapCredentialsId: 'ABAPUserPasswordCredentialsId',
      repository: 'HCL_DevOps_V1'
)


    
    stage("Rollback")
    gctsRollback(
        script: this,
        host: "https://hclutl1909.hcldigilabs.com:8001",
        client: "200",
        abapCredentialsId: 'ABAPUserPasswordCredentialsId',
        repository: "HCL_DevOps_V1"
   )
		
	
	stage('Cleanup')
	
   

}
