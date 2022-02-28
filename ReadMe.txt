Pipeline to deploy Api 

You can find example with values in notion!

1) Change vars. 
   ToolsRoot - folder git init root folder
2) In yaml file
   paths - include

4) In task blackduck specify:
   Go to BlackDuck.com (service to check licenses) and register your project.
   BlackDuckProject, BlackDuckConnectionName

5) task SonarCloudPrepare@1
   Go to sonar.cloud and setup project.
   sonar.inclusions write path to src
  path looks like this **/rootFolderHere/src/**/*

6) task UseDotNet@2
   specify version. But maybe this task is not needed at all, unless 
   new version of .Net appears, which is not bound to Azure Pipline yet.

7) task DotNetCoreCLI@2 specify projects (path to api .sln file) looks like $(ToolsRoot)/Api.sln

8) Check all the names like api-template, api, Template with notion exapmles. Might be some differences


9) In Start.Sonar.yml template SonarCloudPrepare@1 task need to change SonarCloud and organization values.
   
   
   
   