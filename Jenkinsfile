def id = ""
pipeline {
    agent any

    parameters{
            booleanParam(name: 'Linux', defaultValue: false, description:'Seleccione este campo si su Jenkins corre en Linux')
            text(name: 'Token', defaultValue: '', description: 'Ingrese el Token de acceso a IBM Cloud API')
   }

    stages {
        stage("IBM Schematics") {
            
            steps {
                script{
                   // ${id}=${params.Token}
                    powershell ''' echo \${params.Linux} '''
                    
                 
                    
                    
                 
                
                }
            }
        }
    }
}