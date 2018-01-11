    node('master'){
        stage('import'){
            try{
            dir('JenkinsMVC'){
                
                git url :'https://github.com/rdgandhi16/jenkins.git' 
                
            }
            }
            catch(error){
                //slacksend message:{env.BUILD_NUMBER} color:'danger'   
            }
        }
    
        stage('build'){
        try{
            dir('JenkinsMVC'){
                bat 'dotnet restore JenkinsMVC/JenkinsMVC.csproj'
                bat 'msbuild  /t:Rebuild JenkinsMVC/JenkinsMVC.csproj'
                //t means target
                //Rebuild means Clean,Build
            }

            }
            catch(error){
                //slacksend message: color:'danger'                
            }   
        }
        stage('analyze'){
            try{
                dir('JenkinsMVC'){
                    // bat 'C:\\Tools\\SonarQube\\sonarQube.Scanner.MSBuild.exe begin /k: jmvc'
                    // bat 'msbuild /t:build JenkinsMVC.csproj'
                    // bat 'C:\\Tools\\SonarQube\\sonarQube.Scanner.MSBuild.exe end'
                }
            }
            catch(error){
                //slacksend message: color:'danger'
            }
    
        }
        stage('test'){
            try{
                dir('JenkinsMVC.Tests'){
                    // bat 'dotnet restore'
                    // bat 'msbuild /t:build JenkinsMVC.csproj'
                    // bat 'dotnet test'
                }

            }
            catch(error){
                //slacksend message: color:'danger'
            }
    
        }
        stage('package'){
                try{
                    dir('JenkinsMVC'){
                        // bat 'dotnet pack JenkinsMVC.csproj --out ../Package'                        
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
                // bat 'dotnet build ./JenkinsMVC/JenkinsMVC.csproj /p:DeployOnBuild=true /p:PublishProfile=publish'
                // bat 'C:\\Program Files (x86)\\IIS\\Microsoft Web Deploy V3\\msdeploy.exe' 
                // -verb:sync -source:iisApp="C:\\Program Files (x86)\\Jenkins\\workspace\\jenkinsops\\hellopipeline\\JenkinsOps\\obj\\Debug\\netcoreapp2.0\\PubTmp\\Out" 
                // -dest:iisApp="Default Web Site/jenkinsops" computer= username= password=  -enableRule:AppOffline'

            }
            catch(error){
                //slacksend message: color:'danger'                
            }
    
        }
    }
    