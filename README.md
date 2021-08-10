# Examples for skaffold on OpenShift

## Basic nodejs
- uses ubi image for development, and production, but node alpine when debugging
- uses port forward
- Dockerfile configured so the filesystem group `root(0)` has write access to files to be sync to Pod Container

open git repository
```
code skaffold-openshift-examples
```

change directory to example
```
cd nodejs
```

To do development, change a file and sync with remote pod
```
skaffold dev
```
Open browser locally http://127.0.0.1:3000

To do debugging with breakpoints
```
skaffold debug
```

Go to VSCode and use "Attach to Remote", then put a break point for example `nodejs/backend/src/utils/index.js`
Open browser locally http://127.0.0.1:3000 and you will see hit the brake point in VSCode


