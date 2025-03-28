# Reference

<!-- DO NOT EDIT: This document was generated by Puppet Strings -->

## Table of Contents

### Classes

* [`cpanm`](#cpanm): Downloads and installs cpanminus.

### Resource types

* [`cpanm`](#cpanm): Manage CPAN modules with cpanminus

### Data types

* [`Cpanm::HTTPUrl`](#Cpanm--HTTPUrl): Validate a HTTP(S) URL

## Classes

### <a name="cpanm"></a>`cpanm`

Downloads and installs cpanminus.

#### Examples

##### 

```puppet
include cpanm
```

##### 

```puppet
class {'cpanm':
  mirror =>  'http://mirror.my.org/cpan/',
}
```

#### Parameters

The following parameters are available in the `cpanm` class:

* [`installer`](#-cpanm--installer)
* [`manage_dependencies`](#-cpanm--manage_dependencies)
* [`mirror`](#-cpanm--mirror)
* [`lwpbootstraparg`](#-cpanm--lwpbootstraparg)

##### <a name="-cpanm--installer"></a>`installer`

Data type: `Cpanm::HTTPUrl`

Url to the cpanm installer.

Default value: `'https://cpanmin.us'`

##### <a name="-cpanm--manage_dependencies"></a>`manage_dependencies`

Data type: `Boolean`

Wether this module should manage the following dependencies
- perl
- perl-core (rhel7)
- make
- gcc

Default value: `true`

##### <a name="-cpanm--mirror"></a>`mirror`

Data type: `Optional[Cpanm::HTTPUrl]`

A CPAN mirror to use to retrieve App::cpanminus. This is passed to
`cpanm` as `--from`, meaning that only this mirror will be used.

Default value: `undef`

##### <a name="-cpanm--lwpbootstraparg"></a>`lwpbootstraparg`

Data type: `Boolean`

cpanminus bootstrap arguments

Default value: `false`

## Resource types

### <a name="cpanm"></a>`cpanm`

Manage CPAN modules with cpanminus

#### Properties

The following properties are available in the `cpanm` type.

##### `ensure`

Valid values: `absent`, `present`, `installed`, `latest`

Aliases: `"installed"=>"present"`

The basic property that the resource should be in.

Default value: `installed`

#### Parameters

The following parameters are available in the `cpanm` type.

* [`force`](#-cpanm--force)
* [`mirror`](#-cpanm--mirror)
* [`name`](#-cpanm--name)
* [`provider`](#-cpanm--provider)
* [`test`](#-cpanm--test)

##### <a name="-cpanm--force"></a>`force`

Force installation

Default value: `false`

##### <a name="-cpanm--mirror"></a>`mirror`

URL of the CPAN mirror to use

##### <a name="-cpanm--name"></a>`name`

namevar

The CPAN module to manage

##### <a name="-cpanm--provider"></a>`provider`

The specific backend to use for this `cpanm` resource. You will seldom need to specify this --- Puppet will usually
discover the appropriate provider for your platform.

##### <a name="-cpanm--test"></a>`test`

Run CPAN module tests

Default value: `false`

## Data types

### <a name="Cpanm--HTTPUrl"></a>`Cpanm::HTTPUrl`

Validate a HTTP(S) URL

Alias of `Pattern[/(?i:\Ahttps?:\/\/.*\z)/]`

