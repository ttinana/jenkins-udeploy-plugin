jenkins-udeploy-plugin
======================

A plugin for IBM Urban Code Deploy that adds process steps to control Jenkins, launching jobs and executing scripts.

A typical use case is to launch tests after a deployment.<br/>
You can deploy your application using IBM Urban Code Deploy (UCD) as usual, then use this plugin to trigger some test jobs in Jenkins that will validate this deployment.<br/>
The job result status (SUCCESS, FAILED, UNSTABLE) is available as an output property in the UCD step. You can use it for example to set a status on the component(s) version(s) you just deployed.<br/>
This way, UCD is fully master and store all statuses, while you keep your good old Jenkins to run the tests.<br/>

This plugin provides two steps:
- a step to run a jenkins job, giving it some parameters and getting back the job result status. Timeout handling is included.
- a step to run a jenkins system groovy script (as in the script console, see https://wiki.jenkins-ci.org/display/JENKINS/Jenkins+Script+Console), basically allowing you to control Jenkins in any way

The plugin assumes your Jenkins is secured (we are in real life, aren't we?). So you will need to feed in UCD your jenkins server URL, as well as a user name and password (who has permission to run jobs and scripts in Jenkins).

_Notice that there is another UCD-Jenkins plugin (https://developer.ibm.com/urbancode/plugin/jenkins/) that provides integration on the other side, to publish Jenkins builds to UCD_



