# gitopsflux


kubectl create ns flux

export GHUSER="YOURUSER"
fluxctl install \
--git-user=${GHUSER} \
--git-email=${GHUSER}@users.noreply.github.com \
--git-url=git@github.com:${GHUSER}/flux-get-started \
--git-path=namespaces,workloads \
--namespace=flux | kubectl apply -f -


kubectl -n flux rollout status deployment/flux

for installation flux on mac 

brew install fluxctl

for ssh key config

fluxctl identity --k8s-fwd-ns flux

to test it in minikube use below for tunnel
minikube service --url docker-nodejs-demo -n demo
