# Initializing Repositories

## Description

This will walk a user through the initialization of a repository in Hypper.

## Steps

Now we need to initialize a repository we can do that by running the following command:

```bash
hypper repo add demo https://mattfarina.github.io/demo-hypper-charts/repo
```

Let's make sure we can see this repo:

```bash
hypper repo ls
```

This will give us a list of repo that Hypper has.

This command is similar to what helm has but they are independent of one another. To see this we can run this command:

```bash
helm repo ls
```

The repo isn't there. This is because as `hypper` and `helm` are very similar but they don't share the context.
