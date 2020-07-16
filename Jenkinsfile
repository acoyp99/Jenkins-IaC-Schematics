def id = ""
pipeline {
    agent any

    parameters{
            booleanParam(name: 'Linux', defaultValue: false, description:'Seleccione este campo si su Jenkins corre en Linux')
    }

    stages {
        stage("IBM Schematics") {
            
            steps {
                script{

                    powershell "echo ${params.Linux};$${id}='HOLA ${params.Linux}'"
                    powershell "echo ${id}"
                 
                    
                    
                 
                
                }
            }
        }
    }
}