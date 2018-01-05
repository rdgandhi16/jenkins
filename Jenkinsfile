    node('master'){
        stage('import'){
            try{
               git url :'https://github.com/rdgandhi16/jenkins.git' 
            }
            catch(error){
                //slacksend message:{env.BUILD_NUMBER} color:'danger'   
            }
        }
    
        stage('build'){
        try{
            dir('JenkinsMVC'){
                bat 'dotnet restore'
                bat 'msbuild  /t:clean,build JenkinsMVC.csproj'
                //t means target
                //Rebuild meand Clean,Build
            }

            }
            catch(error){
                //slacksend message: color:'danger'                
            }   
        }
        stage('analyze'){
            try{
                dir('JenkinsMVC'){
                    bat 'C:\\Tools\\SonarQube\\sonarQube.Scanner.MSBuild.exe begin /k: jmvc'
                    bat 'msbuild /t:build JenkinsMVC.csproj'
                    bat 'C:\\Tools\\SonarQube\\sonarQube.Scanner.MSBuild.exe end'
                }
            }
            catch(error){
                //slacksend message: color:'danger'
            }
    
        }
        stage('test'){
            try{
                dir('JenkinsMVC.Tests'){
                    bat 'dotnet restore'
                    bat 'msbuild /t:build JenkinsMVC.csproj'
                    bat 'dotnet test'
                }

            }
            catch(error){
                //slacksend message: color:'danger'
            }
    
        }
        stage('package'){
                try{
                    dir('JenkinsMVC'){
                        bat 'dotnet pack JenkinsMVC.csproj --out ../Package'                        
                        //bat 'msbuild /t:pack JenkinsMVC.csproj'
                        //package will be in jenkins/ws
                    }

            }
            catch(error){
                //slacksend message: color:'danger'                
            }
    
        }
    
        stage('deploy'){
            try{

            }
            catch(error){
                //slacksend message: color:'danger'                
            }
    
        }
    }
    