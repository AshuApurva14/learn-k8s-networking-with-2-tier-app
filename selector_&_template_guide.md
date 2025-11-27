## Selector and Template Use Cases in This YAML:

Selector (matchLabels: app: backend):

Purpose: Tells the Deployment which Pods to manage and monitor
In this file: It targets all Pods with the label app: backend
Use case here: Ensures the Deployment controls only the Pods it creates from its template
Template (template: section):

Purpose: Defines the blueprint for creating new Pods
In this file: Specifies that each Pod should have the label app: backend and run the ghcr.io/learnk8s/jobs-api image on port 3000
Use case here: When the Deployment needs to create or recreate a Pod (initial startup or if one crashes), it uses this template

## Broader Kubernetes Use Cases:

Selector:

Used by multiple controllers (Deployments, StatefulSets, DaemonSets) to identify which Pods they own
Enables dynamic management — if a Pod crashes, the selector finds it and the controller recreates it
Allows Services to route traffic to the correct Pods using the same label selector
Enables loose coupling between Deployments and Pods
Template:

Defines the complete Pod specification (containers, volumes, environment variables, security policies)
Used whenever new Pods need to be created or replaced
Ensures consistency — all Pods created from the same template have identical configurations
Can be updated to roll out new versions of the application (rolling updates).
