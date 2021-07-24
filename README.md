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
  ## 2) describe the created pod
    # kubectl describe pod simple-webapp-oclor
  ## 3) expose the service
    # kubectl port-forward simple-web-app-color 8080:8080 --address 0.0.0.0

# deployment of nginx
  ## 1) create the nginx pod
      # kubectl apply -f nginx-deployment.yml
  ## 2) update the image version in nginx-deployment.yml
      # image: nginx:1.18.0 --> image: nginx
  ## 3) configure the pod with the new version
      # kubectl apply -f nginx-deployment.yml 
  ## 4) create a deployment for scaling
    # kubectl create deployment --image=nginx:1.18.0 nginx-deployment
  ## 5) define 2 replicasets
    # kubectl scale --replicas=2 deployment/nginx-deployment
  
# imperative scripting
  ## 1) Update the used image 
    # kubectl set image deployment/nginx-deployment nginx=nginx
  ## 2) get deployments
    # kubectl get deployments.apps -o wide
  ## 
     # NAME               READY   UP-TO-DATE   AVAILABLE   AGE   CONTAINERS   IMAGES   SELECTOR
     # nginx-deployment   2/2     2            2           17m   nginx        nginx    app=nginx-deployment
  ## 3) get the active replicaset with updated version 
    # kubectl get replicasets.apps -o wide
  ## 
      # NAME                          DESIRED   CURRENT   READY   AGE     CONTAINERS   IMAGES         SELECTOR
      # nginx-deployment-54dcb8f666   2         2         2       7m7s    nginx        nginx          app=nginx-deployment,pod-template-hash=54dcb8f666
      # nginx-deployment-6fcdb8cc74   0         0         0       8m44s   nginx        nginx:1.18.0   app=nginx-deployment,pod-template-hash=6fcdb8cc74
    

    
    
  
