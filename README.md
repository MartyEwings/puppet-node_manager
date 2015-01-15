node_manager
============

# Node_manager module

## Overview

Create and manage Node Manager API endpoints as resources.

## Requirements:

- *nix operating system
- Puppet >= 3.7.1  

## Node_group

Enumerate all node groups
* `puppet resource node_group`<br />

Example output
```
node_group { 'default':
  ensure               => 'present',
  classes              => {'profiles::base' => {}},
  environment          => 'production',
  id                   => '00000000-0000-4000-8000-000000000000',
  override_environment => 'false',
  parent               => '00000000-0000-4000-8000-000000000000',
  rule                 => ['and', ['~', 'name', '.*']],
}
```

### Node_group parameters

* `classes`<br />
Classes that are assigned to the node in hash format.  Elements of the hash
are class parameters. Default (empty hash): `{}`

* `environment`<br />
Environment selected for this node group. Default: `production`

* `id`<br />
Universal ID for the group. This attribute is read-only.

* `override_environment`<br />
Whether or not this group's environment ment setting overrides
all other other environments. Default: `false`

* `parent`<br />
The UID for the data group. Default: ``

* `rules`<br />
An array of classification rules. Default (empty hash): `{}`
