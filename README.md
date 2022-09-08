# Creating Basic K8s Mutating and Validating Webhooks

From K8s documents:
> Admission controllers may be "validating", "mutating", or both. Mutating controllers may modify related objects to 
  the requests they admit; validating controllers may not.
> Admission controllers limit requests to create, delete, modify objects or connect to proxy. They do not limit 
  requests to read objects.

- The admission control process proceeds in two phases. In the first phase, mutating admission controllers are run. 
In the second phase, validating admission controllers are run. Note again that some of the controllers are both
- An admission control webhook is not much more than a webserver

When you do an operation on a resource (e.g. pod) the Kubernetes API server will look at the webhook configurations 
to see if there are any admission controls that it needs to apply. For all matched operations, it will first apply 
the mutating webhooks and then take that resource output and apply that to the validating webhooks


## Links

- [K8s Documents on DAC](https://kubernetes.io/docs/reference/access-authn-authz/extensible-admission-controllers/)
- [Mutating Webhooks](https://trstringer.com/kubernetes-mutating-webhook/)
- [Validating Webhooks](https://trstringer.com/kubernetes-validating-webhook/)
- [Framework for Creating Admission Controllers](https://github.com/slok/kubewebhook/)
- [Dynamic Admission Control with cert-manager](https://trstringer.com/admission-control-cert-manager/)
- [Sidecar Injector Git Repo](https://github.com/morvencao/kube-sidecar-injector)
- [cert-manager](https://cert-manager.io/docs/)
- [K8s CertificateSigningRequests](https://cert-manager.io/docs/usage/kube-csr/)
