---
title: Deployment
---

The app has to run somewhere, generally some virtual server on the cloud.

### Key Concepts

* _Multiple Environments_: An app will typically have several environments to which to deploy. 
  * Production: the environment that is live to end users.
  * Staging: a production-equivalent environment for any final testing and validation. Deploying to this environment is a good test that the deployment process will be smooth in production.
  * Development: a frequently-changing environment that is similar to staging, but has the latest changes from developers. Changes may not be truly ready for production. This provides a way for developers to see changes running live, share them with stakeholders for a preview and feedback, etc.
  * (Ad Hoc): Modern cloud platforms allow us to spin up new environments (app server, database, etc.) that might be useful to demo a specific feature, test a configuration, etc.
* _Deployment Scripts_: Apps typically require various tasks to be run on deployment. For example, it may have to kick off a background worker, run database migrations, etc.

### The STSI Way

* _Automate_ deployment as part of CI. For example, a change to the master branch could trigger a deployment to the production environment. This is why a good CI process that you can trust with your life is important. 
