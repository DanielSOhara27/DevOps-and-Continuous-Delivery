# Homework User Story

## User Story
As an instructor, I want you to build and deploy your application with every
push to your Github repository so that you can understand how to create a simple
build and deploy pipeline.

## Acceptance Criteria
* I should receive a single email per team
* The email should contain the name of the individuals on your team
* The email should contain a link to your Github repository
* The Github repository should not contain any password or secret keys
* The email should contain a link to your Travis CI project
* The email should contain a link to your running application that was deployed
automatically
* I should be able to use the application to upload an image


travis-ci.org

# Travis CI
Travis CI is a build and deployment tool that can be used for free on public
Github repositories.  Sign into Travis CI using your Github credentials to setup
your image gallery repository for automated builds -

http://travis-ci.org

# Handling Sensitive Information
We have kept AWS secret keys and other sensitive information in a local
application.properties file that was not checked into Github.  Now that we are
moving from a local build to a cloud hosted build, we need a strategy to handle
this information.

## Gradle Properties and Travis CI Environment Variables
One approach is to have Gradle fill in the sensitive values during the build.
Gradle is flexible enough to read property values from a config file or from
environment variables.  You can store the values locally in a gradle.properties
file that is not stored in Github. For the Travis CI build, you can set the values
as build environment variables.

### Gradle's Properties File
https://docs.gradle.org/current/userguide/build_environment.html

### Travis CI Environment variables
https://docs.travis-ci.com/user/environment-variables/

### More Info on Gradle Properties
http://mrhaki.blogspot.com/2010/09/gradle-goodness-different-ways-to-set.html
https://bowerstudios.com/node/1066

## Travis CI Encryption
Another possible approach is to encrypt the keys using the Travis CI command
line tool.  Once encrypted, these values can be stored in Github.

https://docs.travis-ci.com/user/encryption-keys/

# Automatically Deploying

##Cloudfoundry
Travis CI can deploy to Cloudfoundry -

https://docs.travis-ci.com/user/deployment/cloudfoundry


## AWS
Travis CI can deploy to AWS using the AWS CodeDeploy service

https://docs.travis-ci.com/user/deployment/codedeploy
