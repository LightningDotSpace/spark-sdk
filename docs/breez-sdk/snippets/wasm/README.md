## Steps to compile the snippets locally

### Using the published npm package

This DFX fork does not run the upstream publish-all-platforms CI. Fetch the published package from npm instead:

```shell
mkdir packages
cd packages

wget $(npm view @breeztech/breez-sdk-spark dist.tarball)
tar xvfz *.tgz
cp package/breez-sdk-spark.tgz ../packages/
rm -rf package
cd ..
```

Then run `yarn` to install the package.

### Building package locally
```shell
cd ../../../../packages/wasm/
make build
yarn pack
```

To use published bindings:
- Replace `"@breeztech/breez-sdk-spark": "file:./packages/breez-sdk-spark.tgz"` in `package.json` with
  - `"@breeztech/breez-sdk-spark": "<package-version>"`
- run `yarn`

## Nix

```
yarn add @breeztech/breez-sdk-spark

nix develop

yarn
tsc
yarn run lint
```