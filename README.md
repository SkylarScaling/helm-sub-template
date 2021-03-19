# helm-sub-template

This is an Application Helm Chart that is a PoC for using a remote repo as 
the core of a set of application Helm charts.

Values and resources here will reference the "parent" library chart, adding 
and overriding values as needed.

To set up the remote repo:

```shell
$ helm repo add [desired-helm-repo-name] [URL] [flags]
```

Example:

```shell
$ helm repo add github-helm-repo 'https://raw.githubusercontent.com/SkylarScaling/helm-core-template/master/' --password <git-token> --username SkylarScaling
```

To update the referenced remote repo:

```shell
$ helm dependency update app-template/
```

To install the app (after logging in to the destination cluster):

```shell
$ helm install [desired-release-name] app-template/
```
