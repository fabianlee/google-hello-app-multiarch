# GoogleCloudPlatform hello-app enhanced with multi-arch ARM target for use with Apple Silicon

This project is directly based on the code from the [GoogleCloudPlatform/kubernetes-engine-samples/quickstarts/hello-app](https://github.com/GoogleCloudPlatform/kubernetes-engine-samples/tree/main/quickstarts/hello-app)

The enhancement is building this GoLang app with multiple architectural targets, so that it can also run on ARM64, specifically Apple Silicon.

The github pipeline takes care of the multi-arch build, and publishes the image to the Github Container Registry.


```
docker pull ghcr.io/fabianlee/google-hello-app-multiarch:1.0
```

# Creating tag that invokes Github Action

```
newtag=v1.0.1
git commit -a -m "changes for new tag $newtag" && git push -o ci.skip
git tag $newtag && git push origin $newtag
```

# Deleting tag

```
# delete local tag, then remote
todel=v1.0.1
git tag -d $todel && git push -d origin $todel
```

