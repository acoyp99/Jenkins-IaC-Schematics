pipeline {
    agent any

    parameters{
            booleanParam(name: 'Linux', defaultValue: false, description:'Seleccione este campo si su Jenkins corre en Linux')
    }

    stages {
        stage("IBM Schematics") {
            steps {
                script{
// LINUX 
                    if(params.Linux == true){
                    sh ''' 
                    token="eyJraWQiOiIyMDIwMDYyNDE4MzAiLCJhbGciOiJSUzI1NiJ9.eyJpYW1faWQiOiJJQk1pZC01NTAwMDVBN05XIiwiaWQiOiJJQk1pZC01NTAwMDVBN05XIiwicmVhbG1pZCI6IklCTWlkIiwiaWRlbnRpZmllciI6IjU1MDAwNUE3TlciLCJnaXZlbl9uYW1lIjoiQXJsZXkgRmVybmFuZG8iLCJmYW1pbHlfbmFtZSI6IkNveSBQw6FleiIsIm5hbWUiOiJBcmxleSBGZXJuYW5kbyBDb3kgUMOhZXoiLCJlbWFpbCI6ImFjb3lwQGlibS5jb20iLCJzdWIiOiJhY295cEBpYm0uY29tIiwiYWNjb3VudCI6eyJ2YWxpZCI6dHJ1ZSwiYnNzIjoiZDc1NmE2YWVmMGVkNGQxOGFkNDNhYTcwY2ZlZjAzM2QiLCJpbXNfdXNlcl9pZCI6IjgxNzc4OTIiLCJpbXMiOiIyMDU5Mzg2In0sImlhdCI6MTU5NDg0NTM3NSwiZXhwIjoxNTk0ODQ4OTc1LCJpc3MiOiJodHRwczovL2lhbS5jbG91ZC5pYm0uY29tL2lkZW50aXR5IiwiZ3JhbnRfdHlwZSI6InVybjppYm06cGFyYW1zOm9hdXRoOmdyYW50LXR5cGU6YXBpa2V5Iiwic2NvcGUiOiJpYm0gb3BlbmlkIiwiY2xpZW50X2lkIjoiYngiLCJhY3IiOjEsImFtciI6WyJwd2QiXX0.44iBDiObDIqlbdOpcMrySTmah-q7t95Nz1Q0BgZF-FqjFk1vyx3HJBjbWW-pUpteG-ttbqmgXPbivlPbxWSWYvhoHPtVeBSztxXMO6JrlKij0UuK6Zgb3f2msu7yqNJcwCipoF3g79qSXDDfQcweW4xvO_78PZ0Eq-TJeJFuVcdiKGRvxcRKe2R9Vv5k8KJ4C6i7fQHO4dsExAT4P0mfIEd0cwk_edHoq6Pq9Y9LleWF0DA9ESDzq4kqV78Bq1Lh9zMv1VFhKRLCjpRbntLLhsHfiJ1uEW2gJcj4S8u7XxeaiY_qrYaJE4JMwIUE-tX9YM8rusPKYopeBoa2GhiMpw"
                    id=$(curl --request POST --url https://schematics.cloud.ibm.com/v1/workspaces -H "Authorization: $token" -d '{"name":"jenkins","type": ["terraform_v0.12"],"location": "us-east","description": "Demo","resource_group": "Default","tags": [],"template_repo": {"url": "https://github.com/emeloibmco/Skytap-DevOps-Terraform"},"template_data": [{"folder": ".","type": "terraform_v0.12","variablestore": [{"name": "ibmcloud_api_key","value": ""},{"name": "ssh_public","value": "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDAoce7wEGp0Nfxc6yGtYUD9PJTe2VMEcSYuFtQVUyqvqJCJF9dkgg4A5v3em9tvA6W6/BL1YZ20sHjECARir+vbGpphIiBZBw5xmWAEQE/B6Xzh/7f5YjabInunLkLWi9gD1xLBHiRJ9YngQUrM25jUoVQmvaw4rXOkTyt+LJeW8y+68l1qzex48qzLlHRN89iLIhLqisrep5acy9VxI7He76h1TJ8cE0MB3u+y4ni30GweANNFVv15h71WP+q5X3ZIPOfANGDmMm502HEaG/XFHfbuerP+3thDg4U+WbimI165VjDTruDMUXUqWmpsMfBiu+f8M57tqQLdopMwWLf"},{"name": "resource_group","value": "Default"}]}]}' | grep -Eo "(jenkins-[0-9a-z-]*)" | tail -n 1) 
                    echo "WorkSpace creado!"              
                    echo $id
                    sleep 10
                    curl -X POST https://schematics.cloud.ibm.com/v1/workspaces/$id/plan -H "Authorization: $token" -H "refresh_token: $token"
                    echo "Plan creado!" 
                    '''

                    /* sleep 40
                    curl -X PUT https://schematics.cloud.ibm.com/v1/workspaces/$id/apply -H "Authorization: $token" -H "refresh_token: $token"
                    echo "Plan aplicado!"
                    curl -X PUT https://schematics.cloud.ibm.com/v1/workspaces/jenkins-57c7c629-83ee-40/destroy -H "Authorization: $token" -H "refresh_token: $token"
                    echo "Plan destruido!" */
                }

// WINDOWS
                else{
                    powershell '''
                    $token="eyJraWQiOiIyMDIwMDYyNDE4MzAiLCJhbGciOiJSUzI1NiJ9.eyJpYW1faWQiOiJJQk1pZC01NTAwMDVBN05XIiwiaWQiOiJJQk1pZC01NTAwMDVBN05XIiwicmVhbG1pZCI6IklCTWlkIiwiaWRlbnRpZmllciI6IjU1MDAwNUE3TlciLCJnaXZlbl9uYW1lIjoiQXJsZXkgRmVybmFuZG8iLCJmYW1pbHlfbmFtZSI6IkNveSBQw6FleiIsIm5hbWUiOiJBcmxleSBGZXJuYW5kbyBDb3kgUMOhZXoiLCJlbWFpbCI6ImFjb3lwQGlibS5jb20iLCJzdWIiOiJhY295cEBpYm0uY29tIiwiYWNjb3VudCI6eyJ2YWxpZCI6dHJ1ZSwiYnNzIjoiZDc1NmE2YWVmMGVkNGQxOGFkNDNhYTcwY2ZlZjAzM2QiLCJpbXNfdXNlcl9pZCI6IjgxNzc4OTIiLCJpbXMiOiIyMDU5Mzg2In0sImlhdCI6MTU5NDg4MzkwMCwiZXhwIjoxNTk0ODg3NTAwLCJpc3MiOiJodHRwczovL2lhbS5jbG91ZC5pYm0uY29tL2lkZW50aXR5IiwiZ3JhbnRfdHlwZSI6InVybjppYm06cGFyYW1zOm9hdXRoOmdyYW50LXR5cGU6cGFzc2NvZGUiLCJzY29wZSI6ImlibSBvcGVuaWQiLCJjbGllbnRfaWQiOiJieCIsImFjciI6MSwiYW1yIjpbInB3ZCJdfQ.Q5GgnfdLjRLc5yLUKvy3ZLV6im7CzD29oA6UHnis0g9F3UI3-K3a5EkvKZL8XK-7i1SOsJR-EXFVD9jLoWsNnQod8xxHO-WgFz3UX7yGlyC6EIlV-G1zgk6bhpj_dXrqa-MMp9xeWtS5Lyf2ZfQXE8kcUmHzVpwfKt9Di1ZwNh51HjaoKxUfG9orAh7VQ_nyYHHMCzKk5X5PemJ49aXM3x5Fu-0wv3cIABaK50aQEuymD9z-7sCyyPRWdaIw_F6h0t12R_vbRKFXykQpJmzI3UPqxLZi0FnqyhNIL8N105cMcKqrOOY8RG6HeMQgJf0AEvTin6_3JEr1oZTrYug3Yw"
                    $id=(Invoke-RestMethod -Uri "https://schematics.cloud.ibm.com/v1/workspaces" -Method "Post" -Headers @{"Authorization" = $token} -Body \'{"name":"VPC-Jenkins","type": ["terraform_v0.11"],"location": "us-south","description": "Demo","resource_group": "Default","tags": [],"template_repo": {"url": "https://github.com/acoyp99/Jenkins-Terraform"},"template_data": [{"folder": "Template","type": "terraform_v0.11","variablestore": [{"name": "ibmcloud_api_key","value": "HU5KaMf34arRT8c9J8yJqlcK4PiUfT-wMMZfS7ZZ4O_3"},{"name": "ssh_public","value": "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDAoce7wEGp0Nfxc6yGtYUD9PJTe2VMEcSYuFtQVUyqvqJCJF9dkgg4A5v3em9tvA6W6/BL1YZ20sHjECARir+vbGpphIiBZBw5xmWAEQE/B6Xzh/7f5YjabInunLkLWi9gD1xLBHiRJ9YngQUrM25jUoVQmvaw4rXOkTyt+LJeW8y+68l1qzex48qzLlHRN89iLIhLqisrep5acy9VxI7He76h1TJ8cE0MB3u+y4ni30GweANNFVv15h71WP+q5X3ZIPOfANGDmMm502HEaG/XFHfbuerP+3thDg4U+WbimI165VjDTruDMUXUqWmpsMfBiu+f8M57tqQLdopMwWLf"},{"name": "resource_group","value": "Default"}]}]}\').id
                    echo $id
                    echo "WorkSpace Creado!"
                    Start-Sleep -s 10
                    Invoke-RestMethod -Uri https://schematics.cloud.ibm.com/v1/workspaces/$id/plan -Method "Post" -Headers @{"Authorization" = $token ; "refresh_token" = $token}
                    echo "Plan generado!"
                    '''
                    
                    /* Start-Sleep -s 40
                    Invoke-RestMethod -Uri https://schematics.cloud.ibm.com/v1/workspaces/$id/apply -Method "Put" -Headers @{"Authorization" = $token ; "refresh_token" = $token}
                    echo "Plan aplicado!" 
                    Invoke-RestMethod -Uri https://schematics.cloud.ibm.com/v1/workspaces/$id/destroy -Method "Put" -Headers @{"Authorization" = $token ; "refresh_token" = $token}
                    echo "Plan destruido!" */
                
                }
                }
            }
        }
    }
}