# MLOps - Test Task

1. Install Minikube and kubectl
2. Dockerize train.py
  Take into account that the container image:
- reads the data files (*.csv) from the outer persistent storage (local PC or any other accessible storage)
- stores training log (as <model_name>-training.log), validation results (confusion matrix, ROC-AUC, AUC - as images; classification report as <model_name>-classification-report.txt) aligned with the binary file of the trained model (<model_name>.pkl) to the outer persistent storage (local PC or any other accessible storage)
3. Create and run Minikube cluster
4. Prepare kubectl configuration that
- pulls the Docker image from the docker.io container registry
- requests the resources needed (CPU and RAM)
- executes the train.py
- exports training artifacts to the chosen persistent storage
- releases the resources once the training was completed. 
5. Build Docker images and push them to the docker.io (or any other remote) registry, specify version and tag
6. Start Minikube if not started
7. Execute the training using the Minikube cluster and the kubectl configuration. The artifacts must be available on the persistent storage after the resources were released and the Docker image was stopped.
8. Remove the Minikube deployment once to training is finished
9. Automate steps 4-8 using the IaaC tool of preference (Terraform or whatever you prefer)
10. Create a build plan for the load (Helm or whatever you prefer)
11. Test everything, make sure there are no bugs
12. Write a simple README file with all the mandatory fields (briefly). It must be possible reproduce all the steps on a local PC (macOS).
13. Report the approximate time it took you to complete the task
14. Commit and push the source code to a private GitHub repository, share access with @ogurbych
