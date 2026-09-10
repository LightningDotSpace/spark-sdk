## Steps to run locally
1. Get a python wheel for your platform
  - By downloading it from PyPI
  - or by building it locally (this DFX fork does not run the upstream publish-all-platforms CI)
2. Place the wheel in the `snippets/python/packages` folder
3. Run `pip install packages/{NAME_OF_.WHL_FILE}`

### To lint
1. Install pylint `pip install pylint`
2. Run pylint:

```bash
cd snippets/python
pylint -d W0612,W1203,R0903,C0114,C0115,C0116 src
```

