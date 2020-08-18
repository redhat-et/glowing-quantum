# Artifacts Detail

    .
        ├── image                   # Files required for building Jupyter Notebook image
        ├── operator                # Operator artifacts and documentation 
        └── README.md

# Usage

  

## Installation from Image on OpenShift 4

  

This installation method will use the latest version of the operator image that has been built and published to docker hub

  

1. Deploy the custom resource definition (CRD):

```
oc create -f operators-examples/qiskit-dev-operator/operator/deploy/crds/singhp11.io_qiskitplaygrounds_crd.yaml
```

 2. Deploy the RBAC configuration:
```
oc apply -f operators-examples/qiskit-dev-operator/operator/deploy/role.yaml
oc apply -f operators-examples/qiskit-dev-operator/operator/deploy/service_account.yaml
oc apply -f operators-examples/qiskit-dev-operator/operator/deploy/role_binding.yaml
```
 3. Setting up authorization with IBMQ Account token
 Edit the configuration file:
```
vi operators-examples/qiskit-dev-operator/operator/deploy/secret.cfg
[AUTH TOKENS]
token = your_IBMQ_account_token
```
 4. Deploy the secret
```
oc create secret generic qiskit-secret --from-file=qiskit-secret.cfg=operators-examples/qiskit-dev-operator/operator/deploy/secret.cfg
```
 5. Deploy the operator itself:

```
oc apply -f deploy/operator.yaml
```
 6. Wait for the operator pod deployment to complete:
```
watch oc get pods
```

 7. Deploy an instance of the custom resource:
```
oc create -f operators-examples/qiskit-dev-operator/operator/deploy/crds/singhp11.io_v1_qiskitplayground_cr.yaml
```

 8. The notebook is found on the exposed route
```
oc get routes
```
