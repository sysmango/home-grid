pipeline {
      agent { label 'espresso' } 

      stages{
            /* tests for ansible scripts */
            /* YAML linter */
            stage('Yaml Validation') {
                steps{ 
                  //run yamllint parameter required is the path where the playbooks are stored
                  script {
                      parallel(
                              a: {
                                    try{
                                          sh "yamllint -c jenkins/yamllint_config *.yml"
                                    } catch (err) {
                                          echo "yamllint reported errors, continuing with pipeline"
                                          currentBuild.result = 'UNSTABLE' 
					      }                                          
                              },
                              b: {
                                    try{
                                          sh "yamllint -c jenkins/yamllint_config roles/common/*/*.yml"
                                    } catch (err) {
                                          echo "yamllint reported errors, continuing with pipeline"
                                          currentBuild.result = 'UNSTABLE'
					      }
                              },
                              d: {      
                                    try{                        
                                          sh "yamllint -c jenkins/yamllint_config roles/docker-bootstrap/*/*.yml"
                                    } catch (err) {
                                          echo "yamllint reported errors, continuing with pipeline"
                                          currentBuild.result = 'UNSTABLE'
					      }                                          
                              },
                              e: {      
                                    try{                        
                                          sh "yamllint -c jenkins/yamllint_config roles/docker-install/*/*.yml"
                                    } catch (err) {
                                          echo "yamllint reported errors, continuing with pipeline"
                                          currentBuild.result = 'UNSTABLE'
					      }                                          
                              },
                              f: {      
                                    try{                        
                                          sh "yamllint -c jenkins/yamllint_config roles/docker-viz-service/*/*.yml"
                                    } catch (err) {
                                          echo "yamllint reported errors, continuing with pipeline"
                                          currentBuild.result = 'UNSTABLE'
					      }                                          
                              },
                              i: {      
                                    try{                        
                                          sh "yamllint -c jenkins/yamllint_config roles/etcd-install/*/*.yml"
                                    } catch (err) {
                                          echo "yamllint reported errors, continuing with pipeline"
                                          currentBuild.result = 'UNSTABLE'
					      }                                          
                              },
                              j: {      
                                    try{                        
                                          sh "yamllint -c jenkins/yamllint_config roles/flannel-install/*/*.yml"
                                    } catch (err) {
                                          echo "yamllint reported errors, continuing with pipeline"
                                          currentBuild.result = 'UNSTABLE'
					      }                                          
                              },
                              k: {      
                                    try{                        
                                          sh "yamllint -c jenkins/yamllint_config roles/jenkins-service/*/*.yml"
                                    } catch (err) {
                                          echo "yamllint reported errors, continuing with pipeline"
                                          currentBuild.result = 'UNSTABLE'
					      }                                          
                              },
                              l: {      
                                    try{                        
                                          sh "yamllint -c jenkins/yamllint_config roles/jira-service/*/*.yml"
                                    } catch (err) {
                                          echo "yamllint reported errors, continuing with pipeline"
                                          currentBuild.result = 'UNSTABLE'
					      }                                          
                              },
                              m: {      
                                    try{                        
                                          sh "yamllint -c jenkins/yamllint_config roles/mangonet/*/*.yml"
                                    } catch (err) {
                                          echo "yamllint reported errors, continuing with pipeline"
                                          currentBuild.result = 'UNSTABLE'
					      }                                          
                              },
                              n: {      
                                    try{                        
                                          sh "yamllint -c jenkins/yamllint_config roles/monitoring-service/*/*.yml"
                                    } catch (err) {
                                          echo "yamllint reported errors, continuing with pipeline"
                                          currentBuild.result = 'UNSTABLE'
					      }                                          
                              },
                              p: {      
                                    try{                        
                                          sh "yamllint -c jenkins/yamllint_config roles/nfs-client/*/*.yml"
                                    } catch (err) {
                                          echo "yamllint reported errors, continuing with pipeline"
                                          currentBuild.result = 'UNSTABLE'
					      }                                          
                              },
                              q: {      
                                    try{                        
                                          sh "yamllint -c jenkins/yamllint_config roles/nfs-server/*/*.yml"
                                    } catch (err) {
                                          echo "yamllint reported errors, continuing with pipeline"
                                          currentBuild.result = 'UNSTABLE'
					      }                                          
                              },
                              r: {      
                                    try{                        
                                          sh "yamllint -c jenkins/yamllint_config roles/redis-service/*/*.yml"
                                    } catch (err) {
                                          echo "yamllint reported errors, continuing with pipeline"
                                          currentBuild.result = 'UNSTABLE'
					      }                                          
                              },
                              t: {      
                                    try{                        
                                          sh "yamllint -c jenkins/yamllint_config roles/route53-smtp/*/*.yml"
                                    } catch (err) {
                                          echo "yamllint reported errors, continuing with pipeline"
                                          currentBuild.result = 'UNSTABLE'
					      }                                          
                              },
                              u: {      
                                    try{                        
                                          sh "yamllint -c jenkins/yamllint_config roles/sysmango-bootstrap/*/*.yml"
                                    } catch (err) {
                                          echo "yamllint reported errors, continuing with pipeline"
                                          currentBuild.result = 'UNSTABLE'
					      }                                          
                              }
                              )
                        }                  
                 }
            }
            stage('Ansible Lint') {
                                steps{ 
                  //run ansible-lint parameter required is the path where the playbooks are stored
                  script {
                      parallel(
                              a: {
                                    try{
                                          sh "ansible-lint -x ANSIBLE0012,ANSIBLE0013 *.yml"
                                    } catch (err) {
                                          echo "ansible-lint reported errors, continuing with pipeline"
                                          currentBuild.result = 'UNSTABLE' 
					      }                                          
                              },
                              b: {
                                    try{
                                          sh "ansible-lint -x ANSIBLE0012,ANSIBLE0013 roles/common/*/*.yml"
                                    } catch (err) {
                                          echo "ansible-lint reported errors, continuing with pipeline"
                                          currentBuild.result = 'UNSTABLE'
					      }
                              },
                              d: {      
                                    try{                        
                                          sh "ansible-lint -x ANSIBLE0012,ANSIBLE0013 roles/docker-bootstrap/*/*.yml"
                                    } catch (err) {
                                          echo "ansible-lint reported errors, continuing with pipeline"
                                          currentBuild.result = 'UNSTABLE'
					      }                                          
                              },
                              e: {      
                                    try{                        
                                          sh "ansible-lint -x ANSIBLE0012,ANSIBLE0013 roles/docker-install/*/*.yml"
                                    } catch (err) {
                                          echo "ansible-lint reported errors, continuing with pipeline"
                                          currentBuild.result = 'UNSTABLE'
					      }                                          
                              },
                              f: {      
                                    try{                        
                                          sh "ansible-lint -x ANSIBLE0012,ANSIBLE0013 roles/docker-viz-service/*/*.yml"
                                    } catch (err) {
                                          echo "ansible-lint reported errors, continuing with pipeline"
                                          currentBuild.result = 'UNSTABLE'
					      }                                          
                              },
                              h: {      
                                    try{                        
                                          sh "ansible-lint -x ANSIBLE0012,ANSIBLE0013 roles/elk-service/*/*.yml"
                                    } catch (err) {
                                          echo "ansible-lint reported errors, continuing with pipeline"
                                          currentBuild.result = 'UNSTABLE'
					      }                                          
                              },
                              i: {      
                                    try{                        
                                          sh "ansible-lint -x ANSIBLE0012,ANSIBLE0013 roles/ectd-install/*/*.yml"
                                    } catch (err) {
                                          echo "ansible-lint reported errors, continuing with pipeline"
                                          currentBuild.result = 'UNSTABLE'
					      }                                          
                              },
                              j: {      
                                    try{                        
                                          sh "ansible-lint -x ANSIBLE0012,ANSIBLE0013 roles/flannel-install/*/*.yml"
                                    } catch (err) {
                                          echo "ansible-lint reported errors, continuing with pipeline"
                                          currentBuild.result = 'UNSTABLE'
					      }                                          
                              },
                              k: {      
                                    try{                        
                                          sh "ansible-lint -x ANSIBLE0012,ANSIBLE0013 roles/jenkins-service/*/*.yml"
                                    } catch (err) {
                                          echo "ansible-lint reported errors, continuing with pipeline"
                                          currentBuild.result = 'UNSTABLE'
					      }                                          
                              },
                              l: {      
                                    try{                        
                                          sh "ansible-lint -x ANSIBLE0012,ANSIBLE0013 roles/jira-service/*/*.yml"
                                    } catch (err) {
                                          echo "ansible-lint reported errors, continuing with pipeline"
                                          currentBuild.result = 'UNSTABLE'
					      }                                          
                              },
                              m: {      
                                    try{                        
                                          sh "ansible-lint -x ANSIBLE0012,ANSIBLE0013 roles/mangonet/*/*.yml"
                                    } catch (err) {
                                          echo "ansible-lint reported errors, continuing with pipeline"
                                          currentBuild.result = 'UNSTABLE'
					      }                                          
                              },
                              n: {      
                                    try{                        
                                          sh "ansible-lint -x ANSIBLE0012,ANSIBLE0013 roles/monitoring-service/*/*.yml"
                                    } catch (err) {
                                          echo "ansible-lint reported errors, continuing with pipeline"
                                          currentBuild.result = 'UNSTABLE'
					      }                                          
                              },
                              p: {      
                                    try{                        
                                          sh "ansible-lint -x ANSIBLE0012,ANSIBLE0013 roles/nfs-client/*/*.yml"
                                    } catch (err) {
                                          echo "ansible-lint reported errors, continuing with pipeline"
                                          currentBuild.result = 'UNSTABLE'
					      }                                          
                              },
                              q: {      
                                    try{                        
                                          sh "ansible-lint -x ANSIBLE0012,ANSIBLE0013 roles/nfs-server/*/*.yml"
                                    } catch (err) {
                                          echo "ansible-lint reported errors, continuing with pipeline"
                                          currentBuild.result = 'UNSTABLE'
					      }                                          
                              },
                              r: {      
                                    try{                        
                                          sh "ansible-lint -x ANSIBLE0012,ANSIBLE0013 roles/redis-service/*/*.yml"
                                    } catch (err) {
                                          echo "ansible-lint reported errors, continuing with pipeline"
                                          currentBuild.result = 'UNSTABLE'
					      }                                          
                              },
                              t: {      
                                    try{                        
                                          sh "ansible-lint -x ANSIBLE0012,ANSIBLE0013 roles/route53-smtp/*/*.yml"
                                    } catch (err) {
                                          echo "ansible-lint reported errors, continuing with pipeline"
                                          currentBuild.result = 'UNSTABLE'
					      }                                          
                              },
                              u: {      
                                    try{                        
                                          sh "ansible-lint -x ANSIBLE0012,ANSIBLE0013 roles/sysmango-bootstrap/*/*.yml"
                                    } catch (err) {
                                          echo "ansible-lint reported errors, continuing with pipeline"
                                          currentBuild.result = 'UNSTABLE'
					      }                                          
                              }
                       )
                  }                  
            }
      }
      stage('SonarQube analysis') {
            environment {
                scannerHome = tool 'SonarQube-3.3.0.1492'
            }
            steps {
                withSonarQubeEnv('SysMango SonarQube') {
                    sh "${scannerHome}/bin/sonar-scanner -Dsonar.projectKey=home-grid -Dsonar.sources=. -Dsonar.login=e0f0e320aa71842559f7998dfd2af26cf1848f3f"
                }
            }
        }
      // }
	// }
            /* Commented out this stage because syntax check is already done by ansible-lint
            stage('Ansible Playbook Syntax Check') {
                steps{
                  script {                        
                        //running ansible playbook syntax checker"
                        parallel(
                              a: {                        
                                    sh ""//"ansible-playbook --syntax-check *.yml" 
                              },
                              b: {                                    
                                    sh ""//"ansible-playbook --syntax-check group_vars/*.yml" 
                              },
                              c: {                                    
                                    sh ""//"ansible-playbook --syntax-check roles/7zipinstall/tasks/*.yml"
                              },
                              d: {                                    
                                    sh ""//"ansible-playbook --syntax-check roles/HypCreateUsers/tasks/*.yml"
                              },
                              e: {                                    
                                    sh ""//"ansible-playbook --syntax-check roles/IISInstall/tasks/*.yml"
                              },
                              f: {                                    
                                    sh ""//"ansible-playbook --syntax-check roles/HypRegistry_tcpparam/tasks/*.yml"
                              },
                              g: {                                    
                                    sh ""//"ansible-playbook --syntax-check roles/SetPowerPerf/tasks/*.yml"
                              },
                              h: {                                    
                                    sh ""//"ansible-playbook --syntax-check roles/UACDisable/tasks/*.yml"
                              },
                              i: {                                    
                                    sh ""//"ansible-playbook --syntax-check roles/VCinstall/tasks/*.yml"   
                              }
                        )
                  }
                }
            }*/
            /* Commented out this stage because check will not work without connectivity to endpoints
            stage('Ansible Playbook Dry Run') {
                steps{
                  script {  
                        parallel(
                              a: {                        
                                    //running ansible playbook dry run checker"
                                    sh ""//"ansible-playbook --check *.yml"
                              },
                              b: {                                    
                                    sh ""//"ansible-playbook --check group_vars/*.yml"
                              },
                              c: {                                    
                                    sh ""//"ansible-playbook --check roles/7zipinstall/tasks/*.yml"
                              },
                              d: {                                    
                                    sh ""//"ansible-playbook --check roles/HypCreateUsers/tasks/*.yml"
                              },
                              e: {                                    
                                    sh ""//"ansible-playbook --check roles/IISInstall/tasks/*.yml"
                              },
                              f: {                                    
                                    sh ""//"ansible-playbook --check roles/HypRegistry_tcpparam/tasks/*.yml"
                              },
                              g: {                                    
                                    sh ""//"ansible-playbook --check roles/SetPowerPerf/tasks/*.yml"
                              },
                              h: {                                    
                                    sh ""//"ansible-playbook --check roles/UACDisable/tasks/*.yml"
                              },
                              i: {                                    
                                    sh ""//"ansible-playbook --check roles/VCinstall/tasks/*.yml"  
                              }                                   
                        )
                  }                  
                }
            }*/
            stage('Ansible Playbook Analytics Logged') {
                steps{
                  script {
                        //running grep to ensure all ansible playbooks are writing logs analytics team needs"
                        // currently on searching root if want to search all files use **/*.yml
                        def filesToProcess = findFiles(glob: '**.yml')
                        for (def fileToProcess : filesToProcess) {
                              //sh "echo grep hosts ${fileToProcess}"
                              echo "grep hosts ${fileToProcess}"
                        }
                  }                  
                }
            }
      }
//       post { 
//         unstable { 
//             echo 'Todo send a message to slack when pipeline is unstable!'
//         }
//         failure { 
//             echo 'Todo send a message to slack when pipeline fails!'
//         }
//         always { 
//             echo 'Thank you I have been your Jenkins pipeline today, as a worker in the service industry any and all gratuities are welcome!'
//         }
//     }
}


