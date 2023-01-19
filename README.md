# Helm Charts

This repository contains the Helm charts meant to be consumed by ArgoCD.

## Adding a new helm chart

To create a new helm chart in this directory, do the following:

1. Create a new helm chart skeleton

    `helm create <CHARTNAME>`

1. Remove unused parts

    `rm -r <CHARTNAME>/templates/{*.yaml,NOTES.txt,tests}`

1. Remove unused charts directory

    `rm -r <CHARTNAME>/charts`

1. Clear out the values file

    `> <CHARTNAME>/values.yaml`

1. Fill out the \<CHARTNAME\>/Chart.yaml file
1. Add new templates into \<CHARTNAME\>/templates/
1. Template out values into \<CHARTNAME\>/values.yaml
1. Test out the configuration

    `helm template <CHARTNAME>`

1. Write the documentation for the Helm Chart to \<CHARTNAME\>/README.md

---

Oneliner for copy and paste (Will do nothing if directory already exists):
```bash
CHARTNAME=newchart
[ ! -d ${CHARTNAME} ] && helm create ${CHARTNAME} && rm -r ${CHARTNAME}/templates/{*.yaml,NOTES.txt,tests} ${CHARTNAME}/charts && > ${CHARTNAME}/values.yaml
```

## Documentation

[Helm](https://helm.sh/docs/)
