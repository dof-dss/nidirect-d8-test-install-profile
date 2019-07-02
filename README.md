# NIDirect Drupal 8 Test Install Profile

Drupal source code for the NIDirect website: https://www.nidirect.gov.uk.

## Getting started

This repository should be cloned as follows inside the /web directory of a working Drupal 8 NIDirect site:

 git clone git@svegit01.thestables.net:dss/nidirect-d8-test-install-profile.git profiles
 
(after doing this, you should have a 'web/profile/test_profile' directory in your project)

## Updating the install profile

Simply export your current config to the install profile directory like this:

 lando drush config-export --destination=profiles/test_profile/config/sync
 
After doing this, edit profiles/test_profile/config/sync/core.extension.yml and make sure that the install profile is set to 'test_profile' rather than 'standard'. Note that this may involve making two changes towards the bottom of the file, as shown in the following sampel from the end of the core.extension.yml file:

  test_profile: 1000
  theme:
    stable: 0
    classy: 0
    bartik: 0
    seven: 0
    stark: 0
  profile: test_profile
  _core:
    default_config_hash: R4IF-ClDHXxblLcG0L7MgsLvfBIMAvi_skumNFQwkDc

Finally, delete the memcache_admin.settings.yml file from from profiles/test_profile/config/sync
