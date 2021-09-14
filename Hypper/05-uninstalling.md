# Uninstalling with Shared Dependencies

## Description

This will walk a user through the uninstalling a chart using Hypper.

## Steps

Now we want to show how to uninstall using Hypper.

In the previous example we deployed `demoit` now we want to remove it.

To remove it we will run the following command:

```bash
hypper uninstall demoit -n demo
```

And Hypper will let us know it is uninstalled:

```bash
🔥  uninstalling demoit
✅  release "demoit" uninstalled
```

If we check Hypper again:

```bash
hypper ls -A
```

We see that `demoit` is gone:

```bash
NAME   	NAMESPACE  	REVISION	UPDATED                                	STATUS  	CHART         	APP VERSION
demo-a 	demo-a     	1       	2021-09-13 15:29:09.895199 -0400 EDT   	deployed	demo-a-1.0.0  	1.16.0     
demo-b 	demo-b     	1       	2021-09-13 15:29:12.696027 -0400 EDT   	deployed	demo-b-1.0.0  	1.16.0     
demo-c 	demo-c     	1       	2021-09-13 15:29:11.412079 -0400 EDT   	deployed	demo-c-1.0.0  	1.16.0     
traefik	kube-system	1       	2021-08-18 17:48:32.782500316 +0000 UTC	deployed	traefik-1.81.0	1.7.19 
```

If we reinstall `demoit`:

```bash
hypper install demo/demo
```

Hypper will reinstall `demoit` but it checks for it's dependencies and knows they are already there and doesn't try to install them.

```bash
🛳  Installing chart "demo" as "demoit" in namespace "demo"…
👏 Done!
```
