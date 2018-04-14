# K8s Microservices Bootcamp 

This examples deploys a microservices application in Kubernetes (Minikube) along with monitoring using Prometheus and Grafana. The application consists of: 

<ul>
  <li><b>word-server</b>: This is a spring boot application which can be launched with different profiles: 
    - adjective 
    - article
    - noun
    - subject 
    - verb 
  </li>
  <li><b>sentence-server-solution</b>: This is a spring boot application which call the various word servers to construct a complete sentence</li>
</ul>

Prerqeuisits: 
<ul>
  <li>Minikube 0.25+</li>
  <li>Docker 18+</li>
</ul>

How to set it up 
<ul>
  <li>Start minikube using <b>minikube start</b></li>
  <li>cd into minikube directory</li>
  <li>Install Prometheus in the Kubernetes cluster using <b>kubectl create -f prometheus-operator.yml</b>. You can also use directions given at <a href="https://github.com/coreos/prometheus-operator">Prometheus Operator</a></i>
  <li>Install monitoring pods using <b>kubectl create -f monitoring.yml</b></li>
  <li>Install the sentence server solution using <b>kubectl apply -f sentence-application.yml</b>. This spec installs one pod for each word server (adjective, article, noun, subject, verb), sentence server and a service for each in Kubernetes cluster</li>
  <li>Check the minikube dashboard by running <b>minikube dashboard</b> command. Make sure all pods, services are running. </li>
