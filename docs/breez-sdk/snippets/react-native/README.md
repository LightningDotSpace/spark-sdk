## Steps to compile the snippets locally

### Using the published npm package

This DFX fork does not run the upstream `Publish` CI. Fetch the published package from npm instead:

```shell
mkdir packages
cd packages

wget $(npm view @breeztech/breez-sdk-spark-react-native dist.tarball)
tar xvfz *.tgz
cp package/breez-sdk-spark-react-native.tgz ../packages/
rm -rf package
cd ..
```

Then run `yarn` to install the package.

### Building package locally

```shell
cargo install cargo-ndk --version 3.5.4
brew install clang-format
cd ../../../../packages/react-native/
yarn --mode=skip-build
npx patch-package
yarn ubrn:build
yarn prepare
```

To use locally-generated bindings:

- Replace `"@breeztech/breez-sdk-spark-react-native": "0.1.8-dev4"` in `package.json` with
  - `"@breeztech/breez-sdk-spark-react-native": "file:./packages/breez-sdk-spark-react-native.tgz"`
- run `yarn`

## Nix

```bash
yarn add @breeztech/breez-sdk-spark-react-native

nix develop

yarn
tsc
yarn run lint
```
