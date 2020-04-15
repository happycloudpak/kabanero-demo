# Intro
A sample application to visually demonstrate the Knative application routing capability that is installed in Kabanero.
- Blue/Green Deployment
- Canary Deployment

The medium paper: https://medium.com/@zhimin.wen/demo-of-application-routing-of-knative-serving-5d3a22448a53

# How to test 
$ git clone <git url>  
$ cd kabanero-demo  
$ cd back-end  
$ docker build -t happycloudpak/knative-demo-backend .    
$ cd ../front-end   
$ docker build -t happycloudpak/knative-demo-frontend .  
$ docker push happycloudpak/knative-demo-backend  
$ docker push happycloudpak/knative-demo-frontend  
$ oc apply -f demo-frontend.yaml  
$ oc apply -f demo-backend.yaml  
$ oc get ksvc   
Wait until Ready is True, then ..  
$ oc get po   
You will see there is no Pod for this demo app.   

$ oc get rt   
  
Access url of demo-frontend on web browser   
  
$ oc get po   
Now, You can see Pods for this demo app.  

