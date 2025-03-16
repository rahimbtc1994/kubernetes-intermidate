# Change 04-minimal-port-forward cmd
kubectl port-forward -n ${NAMESPACE} nginx-minimal --address 0.0.0.0 8080:80
because i run kind in a vm