# Annotations

## Description

This will walk a user through what are annotations and how Hypper uses them.

## Steps

To easily see how annotations work we can use `helm` to display the chart.

Since `helm` and `hypper` use different context we will need to add this repo to helm:

```bash
helm repo add demo https://mattfarina.github.io/demo-hypper-charts/repo
```

This will show the following:

```bash
"demo" has been added to your repositories
```

Now let's show this chart:

```bash
helm show chart demo/demo
```

We see a few annotations in this chart that `hypper` uses:

`hypper.cattle.io/namespace: demo` this is the respective namespace.

`hypper.cattle.io/release-name: demoit` this is the name of the release.

`hypper.cattle.io/shared-dependencies` this is the list of the shared dependencies that are needed.

`hypper.cattle.io/optional-dependencies` this isn't displayed but is also supported.

In both of the dependencies sections there are a few fields:

`name:` this is the name of the dependency.

`version:` this is the needed version.

`repository:` this is where the repository is located at.
