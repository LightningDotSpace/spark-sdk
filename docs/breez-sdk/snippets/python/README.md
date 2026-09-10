## Steps to run locally
1. Build a python package
  - By downloading from Pypi
  - or by building the wheel locally (this DFX fork does not run the upstream publish-all-platforms CI)
2. Download the wheel artifact for your platform
3. Unzip the artifact in the `snippets/python/packages` folder
4. Run `pip install packages/{NAME_OF_.WHL_FILE}`

### To lint
1. Install pylint `pip install pylint`
2. Run pylint:

```bash
cd snippets/python
pylint -d W0612,W1203,R0903,C0114,C0115,C0116 src
```

