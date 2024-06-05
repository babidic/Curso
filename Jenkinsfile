pipeline
{
    agent any
    environment
    {
        COMANDO = "cmd ipconfig /flushdns"  
    }
    options
    {
    timeout(time:15, unit: "MINUTES") 
    }
    stages
    {
        stage("Informacion de la ciudad")
        {
            steps
            {
                script
                {
			habitantes = 684164
			ciudad = "Sevilla"
			clima = "Mediterraneo"
			condiciones = "despejado y  33C"
			println "Bienvenido a "+ ciudad
			println "Actualmente podemos disfrutar de un clima " + clima+ ", con un dia "+ condiciones
                }
            }
        }
        stage("Ejecucion de comando")
        {
            steps
            {
                script
                {
			bat "ipconfig /flushdns"
                    	echo "Ejecución correcta"
                }
            }
        }
        stage("Variable de entorno")
        {
            steps
            {
                script
                {
					
                   	 echo "Ejecución  de ${env.JOB_NAME}"
			//Identificador de quien lo ejecuta
			echo "Ejecutado por (Identificador) ${env.EXECUTOR_NUMBER}"
			echo "Ejecutado por (nombre) ${env.env.BUILD_USER}"
                   
                    
                }
            }
        }

        
    }
}
