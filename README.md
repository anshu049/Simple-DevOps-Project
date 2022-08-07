# Simple-DevOps-Project!
[Uploading Simple-DevOps-Project.png…]()



Setup To get this repository, run the following command inside your git enabled terminal

$ git clone https://github.com/anshuhtwt/Simple-DevOps-Project.git

you will need Jenkins, Java, Ant and Tomcat installed in your computer to deploy this webpage, once jenkins is setup install these plugins

1)Github

2)Ant

3)Deploy-to-container

4)Warnings-next-generation

5)Build-pipeline

now create 4 freestyle project to build pipeline named accordingly 1)go to first project, configure-->general-->advanced-->use-custom-workspace then source-code-management-->git-->github-url

2)repeat first step and go to build-->invoke-Ant, then in post-build-action-->Record-compiler-warnings-and-static-analysis-results-->tool-->checkstyle-->Report-file-pattern(Checkstyle-result.xml)

3)repeat first step and go to build-->invoke-Ant-->target(junit)-->post-build-action-->Publish-JUnit-test-result-report-->Test-report-XMLs(TestCalculator_JUnitResult.xml)

4)repeat first step and go to build-->invoke-Ant-->Targets(war)-->post-build-action-->deploy-war/ear-to-container-->WAR/EAR-files(**/*.war)-->add-tomcat and give website for local-host where tomcat is running(restart tomcat)

for making pipeline go to first project and configure-->post-build-action-->build-other-project select and save continue till last project at last first-project-->configure-->build-triggers-->polls-scm-->* * * * *

it will be deployed on tomcat

Cheers and Happy Coding :)
