# Puppet::ResourceApi [![codecov](https://codecov.io/gh/puppetlabs/puppet-resource_api/branch/main/graph/badge.svg)](https://codecov.io/gh/puppetlabs/puppet-resource_api)

This is an implementation of the [Resource API specification](https://github.com/puppetlabs/puppet-specifications/blob/master/language/resource-api/README.md).

Find a working example of a new-style providers in the [Palo Alto Firewall module](https://github.com/puppetlabs/puppetlabs-panos/):
* [Type](https://github.com/puppetlabs/puppetlabs-panos/blob/main/lib/puppet/type/panos_address.rb)
* [Base provider](https://github.com/puppetlabs/puppetlabs-panos/blob/main/lib/puppet/provider/panos_provider.rb)
* [Actual provider with validation and xml processing](https://github.com/puppetlabs/puppetlabs-panos/blob/main/lib/puppet/provider/panos_address/panos_address.rb)
* [New unit tests](https://github.com/puppetlabs/puppetlabs-panos/blob/main/spec/unit/puppet/provider/panos_provider_spec.rb) for 100% coverage.

## [Find the full Resource API documentation here](https://puppet.com/docs/puppet/latest/custom_resources.html)

## Related Documents

* The [Resource API specs](https://github.com/puppetlabs/puppet-specifications/blob/master/language/resource-api/README.md) describes details of all the capabilities of this gem.
* The [puppetlabs-hue module](https://github.com/puppetlabs/puppetlabs-hue) is a very simple example for using the Resource API for remote resources.
* The [meraki module](https://github.com/meraki/puppet-module) is a full example for using the Resource API for remote resources.
* This [Introduction to Testing Puppet Modules](https://www.youtube.com/watch?v=GgNrxLfoDF8) talk describes rspec usage in more detail.
* The [RSpec docs](https://rspec.info/documentation/) provide an overview of the capabilities of rspec.
* Read [betterspecs](http://www.betterspecs.org/) for general guidelines on what is considered good specs.


## Deployment

The `puppet-resource_api` gem is part of Puppet from version 6 onward.


## Contributing
We welcome bug reports and pull requests on the Resource API so that we can continue to improve it to the best of our ability. If you would like to contribute, [have a look at our GitHub](https://github.com/puppetlabs/puppet-resource_api) and the [Resource API Backlog](https://github.com/puppetlabs/puppet-resource_api/projects/1).


## Known Issues

There are still a few notable gaps between the implementation and the specification:
* Only a single runtime environment (the Puppet commands) is currently implemented.

Restrictions of puppet:
* `supports_noop` is not effective, as puppet doesn't call into the type under noop at all.
* Attributes cannot be called `title`, `provider`, or any of the [metaparameters](https://puppet.com/docs/puppet/5.5/metaparameter.html), as those are reserved by puppet itself.

Future possibilities:
* [Multiple Providers](https://tickets.puppetlabs.com/browse/PDK-530)
* [Commands API](https://tickets.puppetlabs.com/browse/PDK-847)
