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
                bat 'nuget restore'
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
                    bat 'dotnet build'
                    bat 'C:\\Tools\\SonarQube\\sonarQube.Scanner.MSBuild.exe end'
                }
            }
            catch(error){
                //slacksend message: color:'danger'
            }
    
    }
    stage('test'){
            try{
                

            }
            catch(error){
                //slacksend message: color:'danger'
            }
    
    }
    stage('package'){
            try{

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
    