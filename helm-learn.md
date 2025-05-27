# Helm

1) helm chart = it is a package
2) helm Repo = where all the packages/charts are present
3) helm release = an instance of a chart running in k8s

-> helm commands in docs

1) helm create <helm-repo-name>

foo/
├── .helmignore   # Contains patterns to ignore when packaging Helm charts.
├── Chart.yaml    # Information about your chart
├── values.yaml   # The default values for your templates
├── charts/       # Charts that this chart depends on
└── templates/    # The template files
    └── tests/    # The test files

2) helm install <release-name> <location-helm-chart>

3) helm upgrade <release-name> <location-path-helm-chart> --values <location-path/values.yaml>

4) helm install <release-name> <location-helm-chart> --values <location-path/values.yaml> -f <location-path/values-dev.yaml> -n <namespace-name>

5) helm ls --all-namespaces or helm list <flags>

6) helm status <release>

7) helm repo 

8) helm uninstall --keep-history 

---
1) add repo 
2) install repo 
3) helm search <repo-name>
4) helm status <helm-release-name>
5) helm uninstall <helm-release-name> , helm uninstall <helm-release-name> --keep-history
6) helm history <helm-release-name> -n <namespace>
7) helm ls --all-namespaces -a // which lists even the uninstalled one's and keep-history one's
8) helm rollback <helm-release-name>  <release-number> -n <namespace>
9) 