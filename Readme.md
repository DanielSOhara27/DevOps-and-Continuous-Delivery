# Homework User Story

## User Story
As an instructor, I want you to build and deploy your application with every
push to your Github repository so that you can understand how to create a simple
build and deploy pipeline.

## Acceptance Criteria
* Homework should be submitted via Blackboard and one submission per team
* Please submit a document that :
 * Contains the name of the individuals on your team
 * Contains a link to your Github repository
 * Contains a link to your running application
 * The Github repository should not contain any password or secret keys
 * Contains a link to your Travis CI project
 * Contains a link to your running application that was deployed
automatically
* I should be able to use the application to upload an image


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

The Twelve-Factor apps design pattern gives us a mechanism to handle the application's
configuration -

https://12factor.net/config

# Automatically Deploying

##Cloudfoundry (Recommended)
Travis CI can deploy to Cloudfoundry -

https://docs.travis-ci.com/user/deployment/cloudfoundry


## AWS
Travis CI can deploy to AWS using the AWS CodeDeploy service

https://docs.travis-ci.com/user/deployment/codedeploy
