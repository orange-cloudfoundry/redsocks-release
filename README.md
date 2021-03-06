# BOSH release for redsocks

This BOSH release and deployment manifest deploy a cluster of redsocks.

## Usage

This repository includes base manifests and operator files. They can be used for initial deployments and subsequently used for updating your deployments:

```plain
export BOSH_ENVIRONMENT=<bosh-alias>
export BOSH_DEPLOYMENT=redsocks
git clone https://github.com/cloudfoundry-community/redsocks-boshrelease.git
bosh deploy redsocks-boshrelease/manifests/redsocks.yml
```

If your BOSH does not have Credhub/Config Server, then remember `--vars-store` to allow generation of passwords and certificates.

### Update

When new versions of `redsocks-boshrelease` are released the `manifests/redsocks.yml` file will be updated. This means you can easily `git pull` and `bosh deploy` to upgrade.

```plain
export BOSH_ENVIRONMENT=<bosh-alias>
export BOSH_DEPLOYMENT=redsocks
cd redsocks-boshrelease
git pull
cd -
bosh deploy redsocks-boshrelease/manifests/redsocks.yml
```
