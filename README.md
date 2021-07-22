# kubectl using a manifest 
  ## 1) create a pod  
    # kubectl apply -f pod.yaml 
  ## 2) get the created pods
    # kubectl get pdos
  ## 3) expose the service
    # kubectl port-forward simple-webapp-oclor 8080:8080 --address 0.0.0.0
  ## 4) delete the created pod
    # kubectl delete -f pod.yaml
    
    
  
