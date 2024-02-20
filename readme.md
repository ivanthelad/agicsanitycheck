## install GK 
helm repo add gatekeeper https://open-policy-agent.github.io/gatekeeper/charts
helm install gatekeeper/gatekeeper --name-template=gatekeeper --namespace gatekeeper-system --create-namespace
## To test on OSS GK 
* deploy the [ Constraint template ](forbiddenannotation.yaml)
* deploy the Constraint  [definition](Constraint.yaml)
* deploy the 3 ingress tests [text](testingress.yaml)

