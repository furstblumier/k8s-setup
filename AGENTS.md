# Agent Instructions

## Required cluster context

All Kubernetes, Helm, and Argo CD work in this repository targets the **magi-system** environment. This applies in all cases unless the user explicitly overrides it for a specific request.

- For `kubectl`, use the Kubernetes context `admin@magi-system` explicitly with `--context admin@magi-system`.
- For `helm`, use `--kube-context admin@magi-system`.
- For `argocd`, use only the Argo CD context associated with `magi-system`, passed explicitly with `--argocd-context`. Argo CD contexts are independent of Kubernetes contexts, so verify the mapping before running a command.
- Never fall back to another current or default context.
- If the `magi-system` Argo CD context is missing or its exact name/mapping is unclear, stop and ask the user instead of selecting another context.
- Apply explicit timeouts to network commands.
