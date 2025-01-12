# plugin-user

[![NPM](https://img.shields.io/npm/v/@salesforce/plugin-user.svg?label=@salesforce/plugin-user)](https://www.npmjs.com/package/@salesforce/plugin-user) [![CircleCI](https://circleci.com/gh/salesforcecli/plugin-user/tree/main.svg?style=shield)](https://circleci.com/gh/salesforcecli/plugin-user/tree/main) [![Downloads/week](https://img.shields.io/npm/dw/@salesforce/plugin-user.svg)](https://npmjs.org/package/@salesforce/plugin-user) [![License](https://img.shields.io/badge/License-BSD%203--Clause-brightgreen.svg)](https://raw.githubusercontent.com/salesforcecli/plugin-user/main/LICENSE.txt)

Commands to interact with Users and Permission Sets in a scratch org

This plugin is bundled with the [Salesforce CLI](https://developer.salesforce.com/tools/sfdxcli). For more information on the CLI, read the [getting started guide](https://developer.salesforce.com/docs/atlas.en-us.sfdx_setup.meta/sfdx_setup/sfdx_setup_intro.htm).

We always recommend using the latest version of these commands bundled with the CLI, however, you can install a specific version or tag if needed.

## Install

```bash
sfdx plugins:install user@x.y.z
```

## Issues

Please report any issues at https://github.com/forcedotcom/cli/issues

## Contributing

1. Please read our [Code of Conduct](CODE_OF_CONDUCT.md)
2. Create a new issue before starting your project so that we can keep track of
   what you are trying to add/fix. That way, we can also offer suggestions or
   let you know if there is already an effort in progress.
3. Fork this repository.
4. [Build the plugin locally](#build)
5. Create a _topic_ branch in your fork. Note, this step is recommended but technically not required if contributing using a fork.
6. Edit the code in your fork.
7. Write appropriate tests for your changes. Try to achieve at least 95% code coverage on any new code. No pull request will be accepted without unit tests.
8. Sign CLA (see [CLA](#cla) below).
9. Send us a pull request when you are done. We'll review your code, suggest any needed changes, and merge it in.

### CLA

External contributors will be required to sign a Contributor's License
Agreement. You can do so by going to https://cla.salesforce.com/sign-cla.

### Build

To build the plugin locally, make sure to have yarn installed and run the following commands:

```bash
# Clone the repository
git clone git@github.com:salesforcecli/plugin-user

# Install the dependencies and compile
yarn install
yarn build
```

To use your plugin, run using the local `./bin/run` or `./bin/run.cmd` file.

```bash
# Run using local run file.
./bin/run user
```

There should be no differences when running via the Salesforce CLI or using the local run file. However, it can be useful to link the plugin to do some additional testing or run your commands from anywhere on your machine.

```bash
# Link your plugin to the sfdx cli
sfdx plugins:link .
# To verify
sfdx plugins
```

## Commands

<!-- commands -->
* [`sfdx force:user:create [name=value...] [-a <string>] [-f <string>] [-s] [-v <string>] [-u <string>] [--apiversion <string>] [--json] [--loglevel trace|debug|info|warn|error|fatal|TRACE|DEBUG|INFO|WARN|ERROR|FATAL]`](#sfdx-forceusercreate-namevalue--a-string--f-string--s--v-string--u-string---apiversion-string---json---loglevel-tracedebuginfowarnerrorfataltracedebuginfowarnerrorfatal)
* [`sfdx force:user:display [-v <string>] [-u <string>] [--apiversion <string>] [--json] [--loglevel trace|debug|info|warn|error|fatal|TRACE|DEBUG|INFO|WARN|ERROR|FATAL]`](#sfdx-forceuserdisplay--v-string--u-string---apiversion-string---json---loglevel-tracedebuginfowarnerrorfataltracedebuginfowarnerrorfatal)
* [`sfdx force:user:list [-v <string>] [-u <string>] [--apiversion <string>] [--json] [--loglevel trace|debug|info|warn|error|fatal|TRACE|DEBUG|INFO|WARN|ERROR|FATAL]`](#sfdx-forceuserlist--v-string--u-string---apiversion-string---json---loglevel-tracedebuginfowarnerrorfataltracedebuginfowarnerrorfatal)
* [`sfdx force:user:password:generate [-o <array>] [-v <string>] [-u <string>] [--apiversion <string>] [--json] [--loglevel trace|debug|info|warn|error|fatal|TRACE|DEBUG|INFO|WARN|ERROR|FATAL]`](#sfdx-forceuserpasswordgenerate--o-array--v-string--u-string---apiversion-string---json---loglevel-tracedebuginfowarnerrorfataltracedebuginfowarnerrorfatal)
* [`sfdx force:user:permset:assign -n <string> [-o <array>] [-u <string>] [--apiversion <string>] [--json] [--loglevel trace|debug|info|warn|error|fatal|TRACE|DEBUG|INFO|WARN|ERROR|FATAL]`](#sfdx-forceuserpermsetassign--n-string--o-array--u-string---apiversion-string---json---loglevel-tracedebuginfowarnerrorfataltracedebuginfowarnerrorfatal)

## `sfdx force:user:create [name=value...] [-a <string>] [-f <string>] [-s] [-v <string>] [-u <string>] [--apiversion <string>] [--json] [--loglevel trace|debug|info|warn|error|fatal|TRACE|DEBUG|INFO|WARN|ERROR|FATAL]`

create a user for a scratch org

```
USAGE
  $ sfdx force:user:create [name=value...] [-a <string>] [-f <string>] [-s] [-v <string>] [-u <string>] [--apiversion 
  <string>] [--json] [--loglevel trace|debug|info|warn|error|fatal|TRACE|DEBUG|INFO|WARN|ERROR|FATAL]

OPTIONS
  -a, --setalias=setalias                                                           set an alias for the created
                                                                                    username to reference within the CLI

  -f, --definitionfile=definitionfile                                               file path to a user definition

  -s, --setuniqueusername                                                           force the username, if specified in
                                                                                    the definition file or at the
                                                                                    command line, to be unique by
                                                                                    appending the org ID

  -u, --targetusername=targetusername                                               username or alias for the target
                                                                                    org; overrides default target org

  -v, --targetdevhubusername=targetdevhubusername                                   username or alias for the dev hub
                                                                                    org; overrides default dev hub org

  --apiversion=apiversion                                                           override the api version used for
                                                                                    api requests made by this command

  --json                                                                            format output as json

  --loglevel=(trace|debug|info|warn|error|fatal|TRACE|DEBUG|INFO|WARN|ERROR|FATAL)  [default: warn] logging level for
                                                                                    this command invocation

DESCRIPTION
  Create a user for a scratch org, optionally setting an alias for use by the CLI, assigning permission sets (e.g., 
  permsets=ps1,ps2), generating a password (e.g., generatepassword=true), and setting User sObject fields.

EXAMPLES
  sfdx force:user:create
  sfdx force:user:create -a testuser1 -f config/project-user-def.json profileName='Chatter Free User'
  sfdx force:user:create username=testuser1@my.org email=me@my.org permsets=DreamHouse
  sfdx force:user:create -f config/project-user-def.json email=me@my.org generatepassword=true
```

_See code: [src/commands/force/user/create.ts](https://github.com/salesforcecli/plugin-user/blob/v1.2.7/src/commands/force/user/create.ts)_

## `sfdx force:user:display [-v <string>] [-u <string>] [--apiversion <string>] [--json] [--loglevel trace|debug|info|warn|error|fatal|TRACE|DEBUG|INFO|WARN|ERROR|FATAL]`

displays information about a user of a scratch org

```
USAGE
  $ sfdx force:user:display [-v <string>] [-u <string>] [--apiversion <string>] [--json] [--loglevel 
  trace|debug|info|warn|error|fatal|TRACE|DEBUG|INFO|WARN|ERROR|FATAL]

OPTIONS
  -u, --targetusername=targetusername                                               username or alias for the target
                                                                                    org; overrides default target org

  -v, --targetdevhubusername=targetdevhubusername                                   username or alias for the dev hub
                                                                                    org; overrides default dev hub org

  --apiversion=apiversion                                                           override the api version used for
                                                                                    api requests made by this command

  --json                                                                            format output as json

  --loglevel=(trace|debug|info|warn|error|fatal|TRACE|DEBUG|INFO|WARN|ERROR|FATAL)  [default: warn] logging level for
                                                                                    this command invocation

DESCRIPTION
  Output includes the profile name, org ID, access token, instance URL, login URL, and alias if applicable.

EXAMPLES
  sfdx force:user:display
  sfdx force:user:display -u me@my.org --json
```

_See code: [src/commands/force/user/display.ts](https://github.com/salesforcecli/plugin-user/blob/v1.2.7/src/commands/force/user/display.ts)_

## `sfdx force:user:list [-v <string>] [-u <string>] [--apiversion <string>] [--json] [--loglevel trace|debug|info|warn|error|fatal|TRACE|DEBUG|INFO|WARN|ERROR|FATAL]`

list all authenticated users of an org

```
USAGE
  $ sfdx force:user:list [-v <string>] [-u <string>] [--apiversion <string>] [--json] [--loglevel 
  trace|debug|info|warn|error|fatal|TRACE|DEBUG|INFO|WARN|ERROR|FATAL]

OPTIONS
  -u, --targetusername=targetusername                                               username or alias for the target
                                                                                    org; overrides default target org

  -v, --targetdevhubusername=targetdevhubusername                                   username or alias for the dev hub
                                                                                    org; overrides default dev hub org

  --apiversion=apiversion                                                           override the api version used for
                                                                                    api requests made by this command

  --json                                                                            format output as json

  --loglevel=(trace|debug|info|warn|error|fatal|TRACE|DEBUG|INFO|WARN|ERROR|FATAL)  [default: warn] logging level for
                                                                                    this command invocation

DESCRIPTION
  The original scratch org admin is marked with "(A)"

EXAMPLES
  sfdx force:user:list
  sfdx force:user:list -u me@my.org --json
  sfdx force:user:list --json > tmp/MyUserList.json
```

_See code: [src/commands/force/user/list.ts](https://github.com/salesforcecli/plugin-user/blob/v1.2.7/src/commands/force/user/list.ts)_

## `sfdx force:user:password:generate [-o <array>] [-v <string>] [-u <string>] [--apiversion <string>] [--json] [--loglevel trace|debug|info|warn|error|fatal|TRACE|DEBUG|INFO|WARN|ERROR|FATAL]`

generate a password for scratch org users

```
USAGE
  $ sfdx force:user:password:generate [-o <array>] [-v <string>] [-u <string>] [--apiversion <string>] [--json] 
  [--loglevel trace|debug|info|warn|error|fatal|TRACE|DEBUG|INFO|WARN|ERROR|FATAL]

OPTIONS
  -o, --onbehalfof=onbehalfof                                                       comma-separated list of usernames or
                                                                                    aliases to assign the password to

  -u, --targetusername=targetusername                                               username or alias for the target
                                                                                    org; overrides default target org

  -v, --targetdevhubusername=targetdevhubusername                                   username or alias for the dev hub
                                                                                    org; overrides default dev hub org

  --apiversion=apiversion                                                           override the api version used for
                                                                                    api requests made by this command

  --json                                                                            format output as json

  --loglevel=(trace|debug|info|warn|error|fatal|TRACE|DEBUG|INFO|WARN|ERROR|FATAL)  [default: warn] logging level for
                                                                                    this command invocation

DESCRIPTION
  Generates and sets a random password for one or more scratch org users. Targets the usernames listed with the 
  --onbehalfof parameter or the --targetusername parameter. Defaults to the defaultusername.

  If you haven’t set a default Dev Hub, or if your scratch org isn’t associated with your default Dev Hub, 
  --targetdevhubusername is required.

  To see a password that was previously generated, run "sfdx force:user:display".

EXAMPLES
  sfdx force:user:password:generate
  sfdx force:user:password:generate -u me@my.org --json
  sfdx force:user:password:generate -o "user1@my.org,user2@my.org,user3@my.org"
```

_See code: [src/commands/force/user/password/generate.ts](https://github.com/salesforcecli/plugin-user/blob/v1.2.7/src/commands/force/user/password/generate.ts)_

## `sfdx force:user:permset:assign -n <string> [-o <array>] [-u <string>] [--apiversion <string>] [--json] [--loglevel trace|debug|info|warn|error|fatal|TRACE|DEBUG|INFO|WARN|ERROR|FATAL]`

assign a permission set to one or more users of an org

```
USAGE
  $ sfdx force:user:permset:assign -n <string> [-o <array>] [-u <string>] [--apiversion <string>] [--json] [--loglevel 
  trace|debug|info|warn|error|fatal|TRACE|DEBUG|INFO|WARN|ERROR|FATAL]

OPTIONS
  -n, --permsetname=permsetname                                                     (required) the name of the
                                                                                    permission set to assign

  -o, --onbehalfof=onbehalfof                                                       comma-separated list of usernames or
                                                                                    aliases to assign the permission set
                                                                                    to

  -u, --targetusername=targetusername                                               username or alias for the target
                                                                                    org; overrides default target org

  --apiversion=apiversion                                                           override the api version used for
                                                                                    api requests made by this command

  --json                                                                            format output as json

  --loglevel=(trace|debug|info|warn|error|fatal|TRACE|DEBUG|INFO|WARN|ERROR|FATAL)  [default: warn] logging level for
                                                                                    this command invocation

EXAMPLES
  sfdx force:user:permset:assign -n DreamHouse
  sfdx force:user:permset:assign -n DreamHouse -u me@my.org
  sfdx force:user:permset:assign -n DreamHouse -o "user1@my.org,user2,user3"
```

_See code: [src/commands/force/user/permset/assign.ts](https://github.com/salesforcecli/plugin-user/blob/v1.2.7/src/commands/force/user/permset/assign.ts)_
<!-- commandsstop -->
