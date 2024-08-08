---
title : "CKA Exam Experience"
subtitle : "Cleared the Certified Kubernetes Administrator certification"
date : 2024-08-07
tags:
- Certification
- CKA
- kubernetes
- study
---

I cleared the CKA a few days back, and here are some tips from my experiences that might help you in the exam:

### 1. Set Up Your Environment Before Starting the Exam

- **Edit the `~/.bashrc` :**  Enable vim keybindings for bash. Also set force_color_prompt to yes. This is required if you want to have a colourful prompt in your Bash shell while using Tmux.

- **Edit `~/.tmux.conf`:** Enable vi copy mode in Tmux. This becomes very helpful for copying stuff from the terminal/man pages to the output.

> The *vim-edit* (activated by pressing v, in vi mode) can be very helpful while copy pasting long command that need to be edited. ex: While performing a kubeadm node upgrade.


### 2. Store Values in a Variable for Long Commands

- A good example is doing an **etcd backup**. The command for this is usually quite long. 
- Unless the keys and certs are part of the question, you can get the values by running `kubectl describe -n kube-system etcd | grep "/etcd/"` in most cases.
- Store these paths as environment variables, like this:

```bash
end=https://localhost:2379/
cert=/etc/kubernetes/pki/etcd/server.crt
key=/etc/kubernetes/pki/etcd/server.key
cacert=/etc/kubernetes/pki/etcd/ca.crt
```

  Now, the etcd backup command can be done easily as follows.:

```bash
ETCDCTL_API=3 etcdctl --endpoints=$end --cert=$cert --key=$key --cacert=$cacert snapshot save /path/save.db
```

This will also be helpful, in ensuring you're doing the thing right in the first go as well!
### 3. Get Familiar with `journalctl` and Directories/Files Inside `/var/log`

- Troubleshooting is a key part of the exam, so getting comfortable with logging tools in linux can be very helpful. **Getting familiar with troubleshooting the kubelet is essential**. I would suggest practising Kim's Killercoda scenarios, they can be accommodating in this regard.

### 4. Use `man` Pages Efficiently Using `grep`

- Full credit to this goes to  Rio. If you want to look at examples of how the command is run with `kubectl`, use it the following way:

```bash
$ kubectl create ingress -h | grep "kubectl create"
kubectl create ingress simple --rule="foo.com/bar=svc1:8080,tls=my-cert"
kubectl create ingress catch-all --class=otheringress --rule="/path=svc:port"
kubectl create ingress annotated --class=default --rule="foo.com/bar=svc:port" \
kubectl create ingress multipath --class=default \
kubectl create ingress ingress1 --class=default \
kubectl create ingress ingtls --class=default \
kubectl create ingress ingsecret --class=default \
kubectl create ingress ingdefault --class=default \
kubectl create ingress NAME --rule=host/path=service:port[,tls[=secret]] [options]

```

  Similarly, you can do this for other resources as well.

```bash
kubectl auth can-i -h | grep "kubectl auth"
```


I hope these tips help you prepare. Have a great day and good luck with your exam!

Har Har Mahadev 🙏


