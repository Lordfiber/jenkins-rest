```yaml
openapi: 3.0.0
info:
  title: Jenkins-Rest API
  description: Java client is built on the top of jclouds for working with Jenkins REST API.
  version: 0.0.30
  servers:
  - url: http://127.0.0.1:8080
    description: your jenkins working basic url
paths:
	/job/{jobName}/api/json
		get:
			description: >
			This resource represent your personal jenkins job information in the system.
			patameters:
			 	- jobName: jobName
          			in: path
          			required: true
          			description: The name of the jenkins job.
          			schema: 
          				type: string
          	 response: 
          		'200':
          			description: jon information like each build outcom,class,action
          			content:
          				application/json:
          					scheam:
                            	type: object
                            	properties:
                            	_class:org.jenkinsci.plugins.workflow.job.WorkflowJob
                            	actions:
                            		0: {}
                            		1: {}
                            	description: the information you write down when creating a job
                            	displayName: jobName
                            	fullDisplayName: jobName
                            	url: "http://localhost:8080/job/jobName"
                            	builds:
                            		scheam:
                            			type: array
                            			description: return you each build trail
                            		properties: 
                            			0:
                            				_class: org.jenkinsci.plugins.workflow.job.WorkflowRun
                            				number: 2
                            				url: "http://localhost:8080/job/jobName/2"
                            			1:
                            				_class: org.jenkinsci.plugins.workflow.job.WorkflowRun
                            				number: 1
                            				url: "http://localhost:8080/job/jobName/1"
                            	color: red
                          		firstBuild:
                          			1:
                            				_class: org.jenkinsci.plugins.workflow.job.WorkflowRun
                            				number: 1
                            				url: "http://localhost:8080/job/jobName/1"
                            	healthReport:
                            		0:
                            			description: Build stability: 1 out of the last 2 builds faild
                            			iconClassName: icon-health-00to19
                            			inonUrl: health-00to19.png
                            			score:20
                            	lastBuild:
								_class: org.jenkinsci.plugins.workflow.job.WorkflowRun
                            				number: 2
                            				url: "http://localhost:8080/job/jobName/2"
                            	lastCompletedBuild:
                            		_class: org.jenkinsci.plugins.workflow.job.WorkflowRun
                            				number: 2
                            				url: "http://localhost:8080/job/jobName/2"
                            	lastStableBuild:
                            		_class: org.jenkinsci.plugins.workflow.job.WorkflowRun
                            				number: 2
                            				url: "http://localhost:8080/job/jobName/2"
                            	lastSuccessfulBuild:
                            		_class: org.jenkinsci.plugins.workflow.job.WorkflowRun
                            				number: 2
                            				url: "http://localhost:8080/job/jobName/2"
                            	lastUnsuccessfulBuild:
                            		_class: org.jenkinsci.plugins.workflow.job.WorkflowRun
                            				number: 1
                            				url: "http://localhost:8080/job/jobName/1"
                            	nextBuildNumber: 3
                            	property:
                            		0:
                            			_class: com.coravy.hudson.plugins.github.GithubProjectProperty
                            	concureentBuild: true
                            	inQueue: false
                                queueItem: null
                                resumeBlocked: false
				'404':
					description: This page may not exist, or you may not have permission to see it
```

