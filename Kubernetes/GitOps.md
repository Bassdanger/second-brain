• GitOps Definition:
- A set of best practices where the entire code delivery process is controlled via Git
- Includes infrastructure and application definition as code
- Uses automation for updates and rollbacks

• Key GitOps Principles:
- Entire system (infrastructure and applications) is described declaratively
- Desired system state is versioned in Git
- Approved changes are automatically applied to the system
- Software agents ensure correctness and alert on divergence

• GitOps Workflow:
- Git repository holds all configuration for applications and infrastructure
- Cluster pulls changes and deployment information
- GitOps controller runs a constant loop to match Git state with cluster state

• Benefits of GitOps:
- Provides version control and history of all changes
- Enables collaboration through Git workflows
- Improves security by reducing direct cluster access
- Facilitates automation for updates and rollbacks

• Flux vs. Argo CD:
- Flux chosen for this course due to:

• Simpler setup and less overwhelming interface

• Encourages CLI usage and GitOps thinking

• Native integration with Azure Kubernetes Service (AKS)

• Heavy reliance on Kustomize for manifest management

• Kustomize:
- Templating language for Kubernetes manifests
- Allows for declarative management of Kubernetes objects
- Important skill for Kubernetes engineers

• Reasons for Using GitOps in Home Lab:
- Provides practical experience with industry-standard practices
- Creates a public record of learning and skills
- Facilitates collaboration and version control