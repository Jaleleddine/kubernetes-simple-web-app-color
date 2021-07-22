# kubectl using a manifest 
  ## 1) create a pod  
    # kubectl apply -f pod.yaml 
  ## 2) get the created pods
    # kubectl get pdos
  ## 3) expose the service
    # kubectl port-forward simple-webapp-oclor 8080:8080 --address 0.0.0.0
  ## 4) delete the created pod
    # kubectl delete -f pod.yaml

# kubectl using run
  ## 1) create a pod  
    # kubectl run --image=mmumshad/simple-webapp-color --env="APP_COLOR=red" --restart=Never simple-web-app-color 
  ## 2) expose the service
    # kubectl port-forward simple-web-app-color 8080:8080 --address 0.0.0.0
  ## 3) delete the created deployment
    # kubectl create deployment --image=nginx:1.18.0 nginx-deployment
  ## 3) delete the created deployment
    # kubectl scale --replicas=2 deployment/nginx-deployment
  ## 3) delete the created deployment
    # kubectl get deployments.apps -o wide
  ## 3) delete the created deployment
    # kubectl set image deployment/nginx-deployment nginx=nginx
  
      # NAME                          DESIRED   CURRENT   READY   AGE     CONTAINERS   IMAGES         SELECTOR
      # nginx-deployment-54dcb8f666   2         2         2       7m7s    nginx        nginx          app=nginx-deployment,pod-template-hash=54dcb8f666
      # nginx-deployment-6fcdb8cc74   0         0         0       8m44s   nginx        nginx:1.18.0   app=nginx-deployment,pod-template-hash=6fcdb8cc74
    

    
    
  
