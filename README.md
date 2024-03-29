This repo is no longer maintained. You should use [WebPack](https://webpack.js.org/) instead.

# Minipush

Minipush is a tool to minimize css and js files and bundle them for an app. 


## Links:
#### [pypi project](https://pypi.org/project/minipush/)
#### [github repo](https://github.com/merlleu/minipush)

## Install with pypi:
```
pip install minipush
```

### This package supports the followings filetypes: css, js

# Sample config:
```json
{
    "origin": {"folders":["css/", "js/core/", "js/plugins/", "js/"]},
    "destination": {"folder": "../templates/", "exts": ["htm", "html"], "type": "embed", "basefolderlink": "/static/"},
    "anchors": {"js": {"start": "<!--AutomatedJSExport-Start-->",
                "end": "<!--AutomatedJSExport-End-->"},
                "css": {"start": "<!--AutomatedCSSExport-Start-->",
                        "end": "<!--AutomatedCSSExport-End-->"},
                "conf": {"start": "<!--AutomatedExport-Start->",
                        "end": "<-AutomatedExport-End-->"}
                },
    "format":{"embed":{"js": "<!--{filename}--><script>{content}</script>",
                       "css": "<!--{filename}--><style>{content}</style>"},
              "link":{"js": "<script src='{path}'/>",
                      "css": "<link href='{path}' rel='stylesheet'/>"}
            },
    "cache": {"folder": "../static/",
              "enabled": true}
}
```
# Basic example script ([github](https://github.com/merlleu/minipush/blob/master/test/test_basic.py)):
```python
from minipush import Minipush
Minipush(file="config.json").run()
```


# Command mode:
``` python -m minipush [arguments] ```
```
Arguments:
command      argument         description
-c --config  {configfile}     set the json config file to load
-j --json    '{configjson}'   set the config from json
-C --clear                    remove all the scripts from the templates
-h --help                     show help
-v --version                  show version
```

### Copyright (c) 2019 Rémi "Mr e-RL"LANGDORPH - mrerl@warlegend.net (under MIT license)
