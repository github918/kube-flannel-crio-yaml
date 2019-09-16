To get flannel network working with crio, cniVersion is required in the flannel cni configuration.

      "cniVersion": "0.2.0",

I changed the PR to use CNI version 0.2.0 instead of 0.3.1 to preserve backward-compatibility (at least down to Kubernetes 1.11 that uses CNI 0.6.0 with schema version 0.2.0) since the older CNI schema is still supported by current implementations but not the other way around.

See issue: coreos/flannel#1173
