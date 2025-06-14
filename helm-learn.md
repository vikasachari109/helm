# Helm Cheat Sheet

## Key Concepts

- **Helm Chart**: A Helm package containing all resource definitions needed to run an application, tool, or service inside a Kubernetes cluster.
- **Helm Repository**: A collection of Helm charts, similar to a package repository.
- **Helm Release**: An instance of a chart running in a Kubernetes cluster.

---

## Common Helm Commands

### Chart Creation

```sh
helm create <chart-name>
```
Creates a new chart with the following structure:

```
foo/
├── .helmignore   # Patterns to ignore when packaging
├── Chart.yaml    # Chart metadata
├── values.yaml   # Default configuration values
├── charts/       # Chart dependencies
└── templates/    # Kubernetes manifest templates
    └── tests/    # Test files
```

### Installing and Upgrading Charts

- **Install a chart:**
  ```sh
  helm install <release-name> <chart-path>
  ```

- **Install with custom values:**
  ```sh
  helm install <release-name> <chart-path> --values <values.yaml> -f <values-dev.yaml> -n <namespace>
  ```

- **Upgrade a release:**
  ```sh
  helm upgrade <release-name> <chart-path> --values <values.yaml>
  ```

### Listing, Status, and History

- **List releases:**
  ```sh
  helm list --all-namespaces
  ```

- **Get release status:**
  ```sh
  helm status <release-name>
  ```

- **Show release history:**
  ```sh
  helm history <release-name> -n <namespace>
  ```

### Repository Management

- **Add a repository:**
  ```sh
  helm repo add <repo-name> <repo-url>
  ```

- **Update repositories:**
  ```sh
  helm repo update
  ```

- **Search for charts:**
  ```sh
  helm search repo <keyword>
  ```

### Uninstalling and Rollback

- **Uninstall a release:**
  ```sh
  helm uninstall <release-name> [--keep-history]
  ```

- **Rollback to a previous release:**
  ```sh
  helm rollback <release-name> <revision> -n <namespace>
  ```

---

## Notes

- Use `helm list --all-namespaces -a` to list all releases, including uninstalled and those with history kept.
- The `--keep-history` flag preserves release history after uninstalling.

---

For more details, refer to the [Helm documentation](https://helm.sh/docs/).