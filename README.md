Production Kubernets Installation Procedure
---

# 1 Install preparation for k8s
```
./install_k8s.sh
```

# 2 Install first control plane node 
```
kubeadm init --control-plane-endpoint "192.168.122.250:9443" --upload-certs
```

# 3 Install rest control plane node
```
kubeadm join 192.168.122.250:9443 --token wh3qbp.uddvu2c0yu5f7wst --discovery-token-ca-cert-hash sha256:9a597ff94b2359e0b3d9d18add4e741ccab01293d6db3b43ec67d54af7331d2d --control-plane --certificate-key 06513deddea415ecda39b26dc28a027fd4489cfd91ead1b3c60a95e618017fb4
```

# 4 Install all worker nodes
```
kubeadm join 192.168.122.250:9443 --token wh3qbp.uddvu2c0yu5f7wst --discovery-token-ca-cert-hash sha256:9a597ff94b2359e0b3d9d18add4e741ccab01293d6db3b43ec67d54af7331d2d
```

# References
https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/high-availability/
