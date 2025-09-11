# Compilers, Interpreters & Language Working (08/09/25) 



🔹 1. Compiler vs Interpreter :-

Compiler: Translates entire program into machine code (faster execution).

Ex: C, C++ (compiled → binary → run).


Interpreter: Executes code line-by-line (slower, flexible).

Ex: Python, JavaScript.



---

🔹 2. How Python Works :-

1. Python source code (.py) → Interpreter


2. Code is first compiled into bytecode (.pyc)


3. Bytecode is executed by the Python Virtual Machine (PVM)


4. Optional: JIT (Just-In-Time) compilers like PyPy speed up execution.



---

🔹 3. How Other Languages Work :-

C / C++

Source code → Compiler → Machine code (direct execution).


Java

Source code → Compiler → Bytecode (.class) → JVM (interprets / JIT compiles).


JavaScript

Code → JS Engine (e.g., V8) → Parser + Interpreter + JIT → Machine code.


Go / Rust

Source code → Compiler → Binary → Run (like C).



---

🔹 4. Six Phases of Compilation (Universal) :- 

1. Lexical Analysis (Scanner) :-

Breaks code into tokens.

Ex: int x = 5; → int, x, =, 5, ;



2. Syntax Analysis (Parser) :-

Checks grammar via parse tree/AST.

Ex: Verifies assignment statement.



3. Semantic Analysis :-

Checks meaning (type checking, scope rules).

Ex: Can’t add string to int.



4. Intermediate Code Generation (IR) :-

Converts AST → Intermediate Representation (portable).



5. Optimization :-

Improves IR (remove redundancies, loop optimizations).



6. Code Generation :-

IR → Target Machine Code (assembly/binary).




(Additional Phase: Symbol Table Management + Error Handling throughout)


---

🔹 5. Mapping Phases in Languages :-

C / C++ → All 6 phases → Machine Code.

Java → All 6 phases → Bytecode → JVM interprets/JIT compiles.

Python → Mini-compiler (phases 1–4) → Bytecode → PVM interprets.

JavaScript → Parser + Interpreter + JIT → Optimized machine code.



---

🔹 6. Key Takeaways :-

Compiled langs = Faster, optimized binaries.

Interpreted langs = Flexible, slower, but portable.

Modern trend: Hybrid (Bytecode + VM + JIT) → Best of both worlds.



---




# From High-Level Language to Executable + Platform Dependence



🔹 1. Journey of Code (HLL → Executable)

1. High-Level Language (HLL)

Human-readable code (Python, C, Java).



2. Preprocessing (C/C++ only)

Handles macros, header files, directives (#include, #define).



3. Compilation

HLL → Assembly/Intermediate Code

Syntax + semantic checks done here.



4. Assembly

Converts to machine instructions (object code).



5. Linking

Combines multiple object files + libraries into a single executable.



6. Loading & Execution

OS loads executable into memory and CPU runs it.





---

🔹 2. Execution Flow in Different Languages

C/C++
HLL → Compiler → Object Code → Linker → Executable (Platform Dependent)

Java
HLL (.java) → Compiler → Bytecode (.class) → JVM → Machine Code (Platform Independent via JVM)

Python
HLL (.py) → Interpreter → Bytecode (.pyc) → Python Virtual Machine (PVM) → Execution

.NET Languages (C#, VB.NET)
HLL → Compiler → CIL (Common Intermediate Language) → CLR (Common Language Runtime) → Execution



---

🔹 3. Platform Dependent vs Platform Independent

📍 Platform Dependent

Code runs only on the system/architecture it was compiled for.

Ex: C/C++ → compiled into machine code specific to Windows/Linux/Mac.

Requires recompilation for each OS.


📍 Platform Independent

Code runs on any platform with a supporting VM/runtime.

Ex: Java (JVM), Python (PVM), .NET (CLR).

HLL → Intermediate Code → Executed on VM (portable).



---

🔹 4. Key Idea

Native compilation → fast, but platform dependent.

VM/Bytecode → portable, but slightly slower.

Modern JIT compilers (Java HotSpot, PyPy, V8 for JS) bridge the gap: portability + speed.



---

⚡ Quick Mnemonic:
👉 “Write Once, Run Anywhere” = Platform Independent (Java, Python).
👉 “Write Once, Compile Everywhere” = Platform Dependent (C/C++).



---





# OOP Concepts :- 


1. Class & Object

Class: Blueprint with variables + methods.

Object: Instance of a class. Real entity



---

2. Encapsulation

Combine data + methods.

Controlled access with private, protected, public.



---

3. Abstraction

Hide implementation, expose interface.

Achieved with abstract classes / pure virtual functions.



---

4. Inheritance

Deriving new classes from base classes.

Types: Single, Multilevel, Multiple, Hierarchical, Hybrid.



---

5. Polymorphism

Compile-time: Function overloading, operator overloading.

Runtime: Virtual functions → method overriding.



---

6. Method Hiding

Definition: When a derived class defines a function with the same name as one in the base class, but without virtual keyword, the base class method gets hidden (not overridden).

#include <iostream>
using namespace std;

class Base {
public:
    void display() { cout << "Base display\n"; }
};

class Derived : public Base {
public:
    void display() { cout << "Derived display\n"; }  // hides Base::display
};

int main() {
    Derived d;
    d.display();      // Calls Derived version
    d.Base::display(); // Explicit call to Base version
}



7. Constructors & Destructors

Constructor: Auto-invoked at object creation.

Destructor: Auto-invoked at object destruction.



---

8. Friend Functions & Operator Overloading

Friend Function: External function that can access private data.

Operator Overloading: Redefine operators for objects.



---

🔑 Final Takeaways :-

Encapsulation + Abstraction → Organize & simplify.

Inheritance + Polymorphism → Reuse & flexibility.

Method Hiding → Replaces base method (unless explicitly called).

Constructors/Destructors → Object lifecycle.

Friends & Overloading → Extra power/flexibility.




# AI, Data Science, and Acceleration (10/09/25 to 11/09/25) 



🔹 Data Science Foundations

Data Science → Extracting insights from structured/unstructured data.

Pandas → Series (1D) + DataFrames (2D) for data manipulation.

NumPy → Arrays, linear algebra backbone.

Scikit-learn (sklearn) → Classical ML algorithms (SVM, Random Forest, Regression).

TensorFlow / PyTorch → Deep Learning frameworks for neural networks.



---

🔹 Math Backbone

Matrix / Linear Algebra → Foundation of ML/DL (vector spaces, transformations).

Dimensions →

Scalar = 0D (single value)

Vector = 1D (array)

Matrix = 2D

Tensor = n-D (generalization).




---

🔹 AI & Advanced Concepts

Deep Learning → Neural networks with multiple hidden layers.

RAG (Retrieval Augmented Generation) → Combines LLMs with external knowledge bases.

Graph RAG → Extends RAG using graph databases for better context + relationships.

Agents → Autonomous AI units (e.g., LangChain agents) that plan, reason, and act.

MCP in AI (Multi-Component Pipeline) → Breaks AI workflows into stages (data prep → training → inference).

VPP in AI (Vector Packet Processing) → High-performance networking for AI workloads (fast data movement).



---

🔹 System / Hardware Acceleration

Path (SR-IOV, DPDK, eBPF)

SR-IOV → Direct NIC access to VM (faster I/O).

DPDK → User-space packet processing (high speed).

eBPF → Kernel-level programmable hooks (efficient packet filtering).


Offload to Workload → Push heavy compute (encryption, ML ops) to accelerators (GPUs, TPUs, SmartNICs).

Cryptoaccelerators → Hardware for cryptography (AES, RSA, SSL offload).

PCIE → High-speed bus connecting CPU ↔ GPU/accelerators.



---

🔹 Relation Flow

1. Data Science stack: NumPy → Pandas → Scikit-learn → TensorFlow.


2. Math Core: Linear algebra + tensors = foundation of ML/DL.


3. Advanced AI: RAG/Graph RAG + Agents enhance LLMs.


4. Pipelines: MCP = modular AI workflow, VPP = high-speed data handling.


5. System Optimization: SR-IOV, DPDK, eBPF for networked AI workloads.


6. Acceleration: Offload ML tasks to GPUs/TPUs over PCIe; cryptoaccelerators secure workloads.




---





# Cloud Computing (9/09/25) 


🌐 Exposing Nginx on AWS + Securing with Let’s Encrypt

1. Setup AWS VM (EC2 Instance) :-

Launch an EC2 Instance (Ubuntu/Debian/RedHat).

Assign a Public IP (or Elastic IP for permanence).

Security Group: Open ports → 22 (SSH), 80 (HTTP), 443 (HTTPS).



---

2. Install Nginx :-

sudo apt update
sudo apt install nginx -y

Start service:


sudo systemctl start nginx
sudo systemctl enable nginx

Verify: Visit http://<Public-IP> → Default Nginx page should appear.



---

3. Expose Nginx on Public IP :-

AWS automatically maps Public IP → Private IP.

Ensure UFW / iptables allows 80, 443:


sudo ufw allow 'Nginx Full'

Test: Access via browser → http://<EC2-Public-IP>.



---

4. Map Domain Name (Optional, Recommended) :-

Buy/register a domain (Route53, GoDaddy, etc.).

Create an A Record → Point domain → EC2 Public IP.

Test: http://yourdomain.com.



---

5. Install Certbot (Let’s Encrypt):- 

Install:


sudo apt install certbot python3-certbot-nginx -y

Obtain SSL Certificate:


sudo certbot --nginx -d yourdomain.com -d www.yourdomain.com

Certbot will:

Edit Nginx config.

Redirect HTTP → HTTPS.

Install certificates in /etc/letsencrypt/.




---

6. Auto-Renew SSL :- 

Certificates valid 90 days.

Enable cron renewal:


sudo systemctl enable certbot.timer
sudo systemctl start certbot.timer

Test renewal:


sudo certbot renew --dry-run


---

7. Final Verification :- 

Access site via:

https://yourdomain.com → Should show 🔒 Secure Padlock.


Nginx config (/etc/nginx/sites-available/default) should auto-contain HTTPS blocks:


server {
    listen 443 ssl;
    server_name yourdomain.com www.yourdomain.com;
    ssl_certificate /etc/letsencrypt/live/yourdomain.com/fullchain.pem;
    ssl_certificate_key /etc/letsencrypt/live/yourdomain.com/privkey.pem;
}


---


Exposing Nginx using K3s on AWS :-


---

1. Install K3s (Single Node Master on AWS VM)

curl -sfL https://get.k3s.io | sh -

Verify:

sudo kubectl get nodes


---

2. Deploy Nginx on K3s :-

sudo kubectl create deployment nginx --image=nginx

Check pods:

sudo kubectl get pods


---

3. Expose Nginx Service :-

Option A: NodePort (Basic Exposure)

sudo kubectl expose deployment nginx --type=NodePort --port=80
sudo kubectl get svc

Note the NodePort (e.g., 30080).

Access via:

http://<AWS-Public-IP>:<NodePort>



---


# Multiple Approaches for hosting website in AWS

Apache (Service) → Docker → Minikube → Kubernetes → AWS private cloud hosting.



# All about Traefik and FRP in AWS


🚦 Traefik in AWS

🔹 What is Traefik?

A modern reverse proxy + load balancer + ingress controller.

Works inside Kubernetes (like K3s, EKS) and in standalone Docker/VM setups.

Automatically configures routes via service discovery (Docker, K8s, Consul, etc.).


🔹 Use Cases in AWS:

1. Ingress Controller in K3s/EKS

Routes traffic from AWS Load Balancer → Kubernetes services.

Supports HTTPS via Let’s Encrypt out of the box.



2. Reverse Proxy for Microservices on EC2/Docker :-

Instead of configuring Nginx/Apache manually, Traefik auto-discovers containers.



3. Load Balancing Across Services :-

Traefik balances requests across multiple EC2 instances / pods.



4. Security :- 

TLS termination (HTTP → HTTPS).

Rate limiting, middleware, authentication.




✅ Example:

AWS VM runs K3s.

Traefik is default ingress in K3s.

User requests → AWS Public IP / Domain → Traefik Ingress → Routes to correct Nginx Service.



---

🔌 FRP (Fast Reverse Proxy)

🔹 What is FRP?

A reverse proxy application to expose a local (private) service to the public internet.

Commonly used when:

The service runs behind NAT/Firewall.

You don’t have a public IP.



🔹 Components:

1. FRP Server (frps)

Runs on a public server (e.g., AWS VM with public IP).

Listens for incoming requests.



2. FRP Client (frpc) :- 

Runs on the local machine (private LAN / localhost).

Connects to the FRP server.

Tunnels requests from the public server back to the local app.




🔹 Workflow:

User → AWS Public IP:Port (frps) → FRP Client → Local Service (e.g., Nginx at localhost:8080).



---

🔹 Use Cases of FRP:

Expose Localhost Websites: Host web apps running on laptop → accessible via AWS.

Testing Webhooks: Receive GitHub/Stripe webhooks on local machine without deploying.

Private Cloud → Public Internet: Connect private VMs/services to AWS without Elastic IP.

Alternative to ngrok: Lightweight and self-hosted.


✅ Example:

Local Nginx at 127.0.0.1:8080.

AWS EC2 runs frps.

Local machine runs frpc tunneling port 8080 → AWS EC2 port 80.

Access via http://AWS-Public-IP.



---

⚡ Key Difference:

Traefik → Cloud/K8s-native reverse proxy & ingress (production use).

FRP → Tunneling local/private services via public server (dev/testing use).


---
