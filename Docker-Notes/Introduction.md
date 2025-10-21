##### Docker
Docker is a **containerization platform** — it lets you package your application **along with all its dependencies** (like libraries, system tools, environment variables, etc.) into a single _container image_.

This image can run **anywhere** — on your system, on a server, or in the cloud — and it will behave **exactly the same** every time.

---

##### Specific properties
1. **Portable** -> A Docker image runs on any system that supports docker. To share a container , we share an image.
2. **Isolation** ->  Each container has it own isolated environments.
3. **Easy Deployment** -> You can deploy the same docker image to any server.
4. **Consistency across Environments** -> Docker containers run the same way everywhere - development , testing - removing it works on my machine.
5. **Scalability** -> Works well with orchestration tools like kubbernetes to easily scale your application across multiple  machines.
6. **Faster Setup** -> Developers can clone your project and run  :
```
docker compose up
```
   and everything just works.

---


#### Problems occurred , so that we use docker!

- It works on my machine!” — common problem when your code runs fine locally but fails on the server due to different environments.
- Installing dependencies manually (Python, PostgreSQL, Redis, etc.) on each system is messy.
- Managing multiple versions of software (e.g., Python 3.8 vs 3.10) is hard.
- Scaling applications (running multiple copies) is difficult.