## Repos have two main branches: 
  - master(deployed to production) and 
  - staging (deployed to staging).

## When working on a feature or bug fix:
 1. Pull from remote staging repo
 1. Checkout the feature "feature/my_feature" or "bug/my_bug" from local staging
 1. Dev and test locally
 1. Merge into staging locally
 1. Deploy to remote staging repo (which is set to auto deploy through beanstalk to staging site)
 1. Test on staging site
 1. Notify QA with link to staging url
 
## Deploying live:
 if your feature or bug has been approved.
 1. notify QA deploy to production is about to begin.
 1. local checkout master
 1. pull from remote master repo
 1. merge local staging into master
 1. push to master repo (set to manual deploy through beanstalk).
 1. if push is successful then do manual deply
 1. notify QA with link to production url
