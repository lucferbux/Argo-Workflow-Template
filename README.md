# Argo-Workflow-Template
Small project to test some argo workflows

![Header Image](/meta/header.png)

## Requirements

* [Install minikube](https://minikube.sigs.k8s.io/docs/)
* [Install argo locally](https://argoproj.github.io/argo-workflows/quick-start/)

## Steps

1. Start submitting the first workflow with the following command:

```bash
argo submit -n argo --watch simple-workflow.yaml
argo logs -n argo @latest
```

2. Check the multistep workflow

```bash
argo submit -n argo --watch multi-step-workflow.yaml
argo logs -n argo @latest
```

3. Deploy a WorkflowTemplate and then a Workflow calling it

```bash
argo template create -n argo workflow-template.yaml
argo submit -n argo --watch call-template-workflow.yaml
argo logs -n argo @latest
```
