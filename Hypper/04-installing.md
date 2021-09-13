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
