pipeline {
    agent any

    parameters{
            booleanParam(name: 'Linux', defaultValue: false, description:'Seleccione este campo si su Jenkins corre en Linux')
    }

    stages {
        stage("IBM Schematics") {
            parameters{
            booleanParam(name: 'Linux2', defaultValue: false, description:'Seleccione este campo si su Jenkins corre en Linux')
    }
            
            steps {
                script{

                    powershell '''

                    echo \"${params.Linux}
                 
                    '''
                    
                 
                
                }
            }
        }
    }
}