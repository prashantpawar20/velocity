pipeline
{

	agent 
	    {
		label
		    {
			label 'built-in'
			}


             }
	
	stages
	{
		stage('built_in_server')
		  {
                     steps
			{	
			  sh 'sudo yum remove httpd -y'
			  sh 'sudo yum install httpd -y'
			  sh 'sudo service httpd start'
			  
			}
		
		  }
                 
                 stage(slave_server1)
                   {
                      agent
                        {
                          label{
				 label '172.31.46.179'
				} 
			}
			
			steps
			 {
			   sh 'sudo yum remove httpd -y'
			   sh 'sudo yum install httpd -y'
			   sh 'sudo cp -r /root/.git/velapp/index1.html /var/www/html'
			   sh 'sudo chmod -R 777 /root/.git/velapp/index1.html'
			 }
			
			
                   } 
                
                 stage(slave_server2)
                   {
                      agent
                        {
                          label{
                                 label '172.31.36.163'
                                }
                        }

                        steps
                         {
                           sh 'sudo yum remove httpd -y'
                           sh 'sudo yum install httpd -y'
                           sh 'sudo cp -r /root/.git/velapp/index2.html /var/www/html'
                           sh 'sudo chmod -R 777 /root/.git/velapp/index2.html'
                         }


                   }

			
	}

}
