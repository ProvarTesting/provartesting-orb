# Orb Project Template

[![CircleCI Build Status](https://circleci.com/gh/ProvarTesting/provartesting-orb.svg?style=shield "CircleCI Build Status")](https://circleci.com/gh/ProvarTesting/provartesting-orb) [![CircleCI Orb Version](https://badges.circleci.com/orbs/provartesting/provar)](https://circleci.com/orbs/registry/orb/provartesting/provar) [![GitHub License](https://img.shields.io/badge/license-MIT-lightgrey.svg)](https://raw.githubusercontent.com/ProvarTesting/provartesting-orb/master/LICENSE) [![CircleCI Community](https://img.shields.io/badge/community-CircleCI%20Discuss-343434.svg)](https://discuss.circleci.com/c/ecosystem/orbs)



A starter template for orb projects. Build, test, and publish orbs automatically on CircleCI with [Orb-Tools](https://circleci.com/orbs/registry/orb/circleci/orb-tools).

Additional READMEs are available in each directory.

## Usage

Example use-cases are provided on the orb [registry page](https://circleci.com/orbs/registry/orb/provartesting/provartesting-orb#usage-examples). Source for these examples can be found within the `src/examples` directory.

## Known Issue

You may get this error when pushing a new PR:
```
The dev version of ministryofjustice/hmpps@dev:alpha has expired. Dev versions of orbs are only valid for 90 days after publishing.
```

If you see this error, you need to publish a dev:alpha version manually. The fix is to run this:

```
circleci orb pack ./src | circleci orb validate -
circleci orb pack ./src | circleci orb publish -  provartesting/provar@dev:alpha
```

You may also get an error if the `dev:alpha` version is out of date and there are config changes in the latest orb that aren't in the dev alpha version.
## Resources

[CircleCI Orb Registry Page](https://circleci.com/orbs/registry/orb/provartesting/provartesting-orb) - The official registry page of this orb for all versions, executors, commands, and jobs described.
[CircleCI Orb Docs](https://circleci.com/docs/2.0/orb-intro/#section=configuration) - Docs for using and creating CircleCI Orbs.

### How to Contribute

We welcome [issues](https://github.com/ProvarTesting/provartesting-orb/issues) to and [pull requests](https://github.com/ProvarTesting/provartesting-orb/pulls) against this repository!

### How to Publish
* Create and push a branch with your new features.
* When ready to publish a new production version, create a Pull Request from _feature branch_ to `main`.
* The title of the pull request must contain a special semver tag: `[semver:<segement>]` where `<segment>` is replaced by one of the following values.

| Increment | Description|
| ----------| -----------|
| major     | Issue a 1.0.0 incremented release|
| minor     | Issue a x.1.0 incremented release|
| patch     | Issue a x.x.1 incremented release|
| skip      | Do not issue a release|

Example: `[semver:major]`

* Squash and merge. Ensure the semver tag is preserved and entered as a part of the commit message.
* On merge, after manual approval, the orb will automatically be published to the Orb Registry.


For further questions/comments about this or other orbs, visit the Orb Category of [CircleCI Discuss](https://discuss.circleci.com/c/orbs).

