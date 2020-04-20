# klog-logrus
Logger adapter for applications that use logrus as main logger and 3rd party libs that use klog

Insipired by glog-logrus (https://github.com/kubermatic/glog-logrus).

# Usage
In go.mod, use a replace entry for klog:
```
replace (
  k8s.io/klog => github.com/tzvatot/klog-logrus v1.0.0
)
```

When creating the logrus logger, have the following imports:
```
import (
	"k8s.io/klog"
	"github.com/sirupsen/logrus"
)
```
And set it to klog:
```
defaultLogger := logrus.StandardLogger()
klog.SetLogger(defaultLogger)
```
