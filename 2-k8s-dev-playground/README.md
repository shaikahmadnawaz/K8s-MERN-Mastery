# Creating Your Kubernetes Development Playground

Welcome back to our journey of mastering Kubernetes for MERN Stack Developers! In this section, we'll guide you through setting up your very own Kubernetes playground using Minikube on an Ubuntu VM.

### **Getting to Know Minikube and kubectl**

- **What's Minikube?** Minikube is like a mini version of Kubernetes that you can play with on your computer. It helps you learn and try out Kubernetes without bothering your computer too much.
  - **Official Documentation:** If you're curious, you can explore more about Minikube in the [**official documentation**](https://minikube.sigs.k8s.io/docs/start).
- **Why Minikube?** Minikube gives you a safe place to explore Kubernetes. It's like a training ground where you can practice without breaking anything important.
- **What's kubectl? (Command line tool)** kubectl (pronounced cube control) is like your magic wand for talking to Kubernetes. It helps you tell Kubernetes what to do and check if it did it right.
  - **Communicating with Kubernetes:** Think of Kubernetes as a city with a control center. To interact with the city, you need a special tool. This tool is named kubectl. It's like a communicator that connects you to the city's control center using the Kubernetes API.
  - **Official Reference:** To delve deeper into kubectl, you can refer to the [**official Kubernetes documentation**](https://kubernetes.io/docs/reference/kubectl).

### **Basic Requirements for Local Kubernetes**

Before you begin your Kubernetes journey, ensure your system meets these basic requirements:

- 2 CPUs or more
- 2GB of free memory
- 20GB of free disk space
- An internet connection
- A container or virtual machine manager like Docker, QEMU, VirtualBox, or others.

### **What's the Deal with Kubernetes Environments?**

- **Kubernetes Development Environment:** Imagine a special room where you create and test your toy models before showing them to the world. That's what a Kubernetes development environment is. It's your safe space for building and trying things out.
- **Kubernetes Production Environment:** This is where the real toys go for their big show. It's like the stage where your apps perform in front of everyone. It's carefully set up, so everything goes perfectly.

### **Installing Minikube on Your Ubuntu VM**

Follow these steps to set up Minikube on your Ubuntu VM:

1. **Get Some Friends for Minikube:** Your clubhouse needs some friends. Install the things Minikube likes using these secret commands:

   ```bash
   sudo apt-get update
   sudo apt-get upgrade
   sudo apt-get install curl
   sudo apt-get install apt-transport-https
   sudo apt-get install conntrack
   ```

2. **Install Docker:** Docker is a key player in the Kubernetes world. Let's get it on board:

   ```bash
   curl -fsSL https://get.docker.com -o get-docker.sh
   sudo sh get-docker.sh
   ls -l /var/run/docker.sock
   sudo usermod -aG docker $USER && newgrp docker
   ```

   ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691770584523/5f9886e1-5da1-470b-817e-67b3264a0cb6.png)

3. **Install Minikube:** Get Minikube ready for the fun stuff:

   ```bash
   curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
   sudo install minikube-linux-amd64 /usr/local/bin/minikube
   sudo chmod +x /usr/local/bin/minikube
   minikube version
   ```

   ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691770722927/76fcee6a-c114-4243-a777-791880c2e924.png)

4. **Bring kubectl Along:** Your magic wand needs to come along too. Let's get kubectl:

   ```bash
   curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
   sudo mv kubectl /usr/local/bin/kubectl
   sudo chmod +x /usr/local/bin/kubectl
   kubectl version --client
   ```

   ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691770835089/998f16cf-594e-4be8-a0b0-e16d33c576e8.png)

5. **Turn on Minikube:** Fire up Minikube using:

   ```bash
   minikube start --driver=docker
   ```

   ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691771001964/84c65d35-0dae-4a9e-87e1-aec3e2dfff3b.png)

```bash
minikube status
kubectl cluster-info
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691771099828/545354b1-820d-4fc1-9e09-4a8148f6e3cf.png)

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691771669465/20fbf2a9-8059-4dba-8d72-42a2a4604b1a.png)

### **Stopping Your Kubernetes Playground**

Once you're done exploring and learning in your Kubernetes playground, it's important to know how to gracefully shut things down.

**Stopping Minikube:**

To stop Minikube, use the following command:

```bash
minikube stop
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691771562045/bd9741a6-a9a2-4c0a-9693-ad4b813b903f.png)

**Stopping the Kubernetes Cluster:**

To stop the entire Kubernetes cluster, you can do the following:

```bash
minikube delete
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691771653003/ece4bbc2-b29e-48ea-80a7-ae85b8523d1c.png)

### **Wrapping Up**

Remember, when you're not using your Kubernetes playground, it's a good practice to stop Minikube and the cluster to save resources and prevent any unexpected behaviours. You can always start them up again whenever you're ready to dive back into your Kubernetes journey.

In the next part of this series, we'll continue our exploration of Kubernetes by putting your MERN app into containers and unleashing its potential in the Kubernetes environment.

Stay tuned for Part 3, where we'll get hands-on with containerization and Kubernetes orchestration for your MERN application.

Exciting things are ahead on your path to mastering Kubernetes and enhancing your MERN skills!

And don't forget to connect with me on social media to stay updated with the latest tips, tutorials, and guides:

- Connect with me on LinkedIn: [shaikahmadnawaz](https://www.linkedin.com/in/shaikahmadnawaz)
- Follow me on Twitter: [shaikahmadnawaz](https://twitter.com/shaikahmadnawaz)
