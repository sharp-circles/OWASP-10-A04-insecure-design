# OWASP-10-A04-insecure-design

SonarQube SAST local deployment 

### Steps

1. Download / pull the latest docker image for SonarQube community edition, then run it. 

```
docker run -d --name sonarqube -e SONAR_ES_BOOTSTRAP_CHECKS_DISABLE=true -p 9000:9000 sonarqube:community
```

2. Create a project, assign a key, get the token

3. Follow this three-step process to analyze the code and obtain the results (example in .NET)

```
dotnet sonarscanner begin /k:"sharp-circles" /d:sonar.host.url="http://localhost:9000"  /d:sonar.token="<your_token_here>"

dotnet build

dotnet sonarscanner end /d:sonar.token="<your_token_here>" 
```  

4. Access SonarQube GUI and check the new results

### Source article

If you have any doubts, or want to know the process in depth, check the article on the platform. It contains detailed, step-to-step explanations on how to proceed.

You will find information, also, on how to extend security custom configurations, understanding baselining or exploring SAST tools alternatives recommended by NIST organization. 

Find the link here: https://sharpcircles.org/post/wtm10-owasp-10-a04-insecure-design-lab-i-sonarqube-sast-deployment
