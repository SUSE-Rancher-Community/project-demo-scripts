# Installing with Shared Dependencies

## Description

This will walk a user through the installing a chart using Hypper.

## Steps

To install a chart using `hypper` the command is very similar to `helm`:

```bash
hypper install demo/demo
```

The output will look like the following:

```bash
demo v1.0.0
 ├─ demo-a v1.0.0
 └─ demo-b v1.0.0
    └─ demo-c v1.0.0

🛳  Installing chart "demo-a" as "demo-a" in namespace "demo-a"…
🛳  Installing chart "demo-c" as "demo-c" in namespace "demo-c"…
🛳  Installing chart "demo-b" as "demo-b" in namespace "demo-b"…
🛳  Installing chart "demo" as "demoit" in namespace "demo"…
👏 Done!
```

This will give you a dependency diagram to show you what is dependent on what.

This will also output each installation.

If we look at the output we can see that `demo-b` is dependent on `demo-c` we can look at this deeper by using the following command:

```bash
helm show chart demo/demo-b
```

This output looks like this:

```bash
annotations:
  hypper.cattle.io/namespace: demo-b
  hypper.cattle.io/release-name: demo-b
  hypper.cattle.io/shared-dependencies: |
    - name: demo-c
      version: "^1.0.0"
      repository: "https://mattfarina.github.io/demo-hypper-charts/repo"
apiVersion: v2
appVersion: 1.16.0
description: A Helm chart for Kubernetes
name: demo-b
type: application
version: 1.0.0
```

We can then see that there is a shared dependencies in `demo-b` that shows it is dependent on `demo-c`.

Lastly we can see what all was installed with using the following command:

```bash
hypper ls -A
```

And what we will get is a list of what was installed that will match the installation output we looked at earlier:

```bash
NAME   	NAMESPACE  	REVISION	UPDATED                                	STATUS  	CHART         	APP VERSION
demo-a 	demo-a     	1       	2021-09-13 15:29:09.895199 -0400 EDT   	deployed	demo-a-1.0.0  	1.16.0     
demo-b 	demo-b     	1       	2021-09-13 15:29:12.696027 -0400 EDT   	deployed	demo-b-1.0.0  	1.16.0     
demo-c 	demo-c     	1       	2021-09-13 15:29:11.412079 -0400 EDT   	deployed	demo-c-1.0.0  	1.16.0     
demoit 	demo       	1       	2021-09-13 15:29:12.845874 -0400 EDT   	deployed	demo-1.0.0    	1.16.0     
traefik	kube-system	1       	2021-08-18 17:48:32.782500316 +0000 UTC	deployed	traefik-1.81.0	1.7.19 
```
