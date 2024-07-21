GitLab self managed runner for CICD

Step 1: Setup self managed runner in Gitlab
![image](https://github.com/olabadmus/K8s-Projects/assets/34897611/6b4816bd-fb01-4c08-9a28-03df41d2e90e)
![image](https://github.com/olabadmus/K8s-Projects/assets/34897611/14af56aa-005d-487d-900b-273069f7a650)

![image](https://github.com/olabadmus/K8s-Projects/assets/34897611/96e0dfcd-ead9-47e4-b7c1-886b242cc32d)

Step 2: Setup AWS EC2 instance
![image](https://github.com/olabadmus/K8s-Projects/assets/34897611/bd10e122-98ad-4b6d-a6b4-99dd9f860a42)

Step 3: Install Gitlab runner using the following commands for my ubuntu EC2 instance:
        curl -L "https://packages.gitlab.com/install/repositories/runner/gitlab-runner/script.deb.sh" | sudo bash
        sudo apt-get install gitlab-runner
![image](https://github.com/olabadmus/K8s-Projects/assets/34897611/9296d674-2a80-438c-84df-30d28ecc4605)

Step 4: Enable gitlab runner and check status using: sudo systemctl enable --now gitlab-runner sudo systemctl status gitlab-runner <br>
Step 5: Register the runner sudo gitlab-runner register. You’ll be prompted to enter the GitLab instance URL, registration token, and an executor. Enter “https://gitlab.com/”, the registration token you copied earlier, and “shell” respectively
![image](https://github.com/olabadmus/K8s-Projects/assets/34897611/874db196-6ff1-40c1-8685-f3ee829a84a3)

Step 6: Install Docke Engine and add Gitlab CI user to the Docker Group
        sudo usermod -aG docker gitlab-runner
        Restart Docker: sudo systemctl restart docker
![image](https://github.com/olabadmus/K8s-Projects/assets/34897611/5c7350ea-6f87-4299-baad-9240cd995fb7)

Step 7: Create a .gitlab-ci.yml file and define pipeline jobs
![image](https://github.com/olabadmus/K8s-Projects/assets/34897611/9b7ed397-b6c4-49f3-91cd-5b4e64f01f4d)


![image](https://github.com/olabadmus/K8s-Projects/assets/34897611/5f2ef893-3b8e-45f5-b683-b0e616ebc63e)



