# Develop and test microservices with Kubernetes and Helm

## Discover the toolchain
  * Explain overall structure of the toolchain, with CI pipelines feeding into CD pipeline
  * Main benefits:
    * Each component developed as a microservice in its own repo, with Dockerfile (build) and Helm chart (release)
    * CI portion typically would be owned by dev squad, CD portion typically owned by ops squad
    * Set of component version deployed as a snapshot through a Helm umbrella chart (aggregating package component charts)
    * Consistent snapshot rolling deploy to environments through a separate pipeline, promotion through staging and production
    * Using quality gates at all levels of the process, raising the bar progressively
    * Insight also provides global inventory across environments, traceability back to the commit
    * Show vulnerabilities in UI CI pipeline, explain using a vanilla php:apache image. Explain advisor mode for now, but could be strictened
    * TBD - show use of pluggable image in CD pipeline for extra selenium testing
  * Extras
    * Show Slack notifications for all deployment activity
    * Toolchain handling Cloudant service creation, cluster image pull secret
    * Environment properties kept in CD pipeline, fed during deployment. Could feed secrets from pipeline secure properties or another vault
    * Auditable deployed elements in Solution repo
    * Toolchain could deploy to cluster in other regions (or different cluster namespaces in same region)
## Develop a microservice
  * Functional regression (speed with control)
    * Enable new app code in catalog-api causing prod coverage criteria to not be met
    * See quality gate failed before entering production, show Insights dashboard
    * Show traceability back from dashboard into git commit
    * Show red status in Slack (if needed explain pagerduty would have triggered only when actual prod deploy would have failed, but luckily gated)
    * (TBD) Address problem, open issue, revert bad commit (using webide), show traceability back to commit and issue tracker
  * (TBD) Deliver a code change that will cause PagerDuty to trigger, fix it, show traceability to commit and issue tracker
  * (TBD) Prod style regression:
    * Remove CSS file from UI (or remove it from dockerfile only), see outcome is bad layout in prod (should have been caught by selenium tests). 
    * Issue a helm rollback (using pipeline predefined stage) as emergency action
    * Fix it by reverting CSS file, and see all cleared properly, traceability back to commit and issue
## Develop locally 
  * Fetch code locally
  * Run in minikube
## Deploy anywhere
  * Target an ICp cluster available on public network
  * Explain using private pipeline workers in future
## Future enhancements
  * Autoscaling using load test
  * Blue/green deployment across two namespaces
  * Using Istio in future to implement A/B testing