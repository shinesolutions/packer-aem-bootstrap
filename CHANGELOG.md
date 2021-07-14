# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## Unreleased
### Added
- Add certificate creation for AEM 6.5/JDK11 Makefile target

## 5.5.1 - 2021-06-18
### Changed
- Upgrade `aem_curator` to 3.20.1

## 5.5.0 - 2021-06-18
### Changed
- Upgrade `aem_curator` to 3.20.0
- Upgrade default aem_profile to aem65_sp9

## 5.4.0 - 2021-05-01
### Added
- Add jdk type support to ami-ids-examples Makefile target

## 5.3.0 - 2021-04-30
### Changed
- Upgrade `aem_curator` to 3.19.0
- Upgrade default aem_profile to aem65_sp8

## 5.2.1 - 2021-03-12
### Changed
- Update Ansible to 3.1.0

## 5.2.0 - 2021-03-02
### Changed
- Update Ansible to 3.0.0
- Update awscli to 1.19.8
- update boto3 to 1.17.8

## 5.1.0 - 2021-02-11
### Added
- Add aws.install_rng_tools configuration for optimising entropy on instance types which use NVMe
- Avoid overwriting Puppet installation when one is already installed in the source/base AMI [#241]

### Changed
- Lock down pylint to 2.6.0
- Use Python3 virtualenv for GitHub actions
- Use pip3 for python package management
- Convert python scripts to be executed using Python 3
- Use pip3 for Python packages
- Add /bin/aws symlink to /usr/local/aws (boto3)
- Refactor installation of Python packages to be part of O/S
- Use class to install virtualenv package rather than puppet module `tracywebtech-pip`
- Set default Ansible Python interpreter to /usr/bin/python3

### Removed
- Remove puppet module `tracywebtech-pip`

## 5.0.2 - 2020-12-01
### Fixed
- Fixed aem base inspec test

## 5.0.1 - 2020-12-01
### Changed
- Upgrade `ruby_aem` to 3.10.1

## 5.0.0 - 2020-12-01
### Added
- Add new puppet module [adobeinc/dispatcher](https://github.com/adobe/puppet-dispatcher) [shinesolutions/puppet-aem-curator#174]

### Changed
- Upgrade `aem_curator` to 3.18.1
- Upgrade `aem_resources` to 7.2.1
- Upgrade` ruby_aem_aws` version to 2.0.0

## 4.28.1 - 2020-11-27
### Changed
- Replace Travis CI with GitHub Actions
- Upgrade puppet-agent version to 5.5.22

## 4.28.0 - 2020-11-19
### Added
- Add support for all Oracle Java JDK8 versions

### Changed
- Upgrade `aem_curator` to 3.17.0

## 4.27.0 - 2020-11-13
### Added
- Add support to retrieve SSL Certificate from IAM to support 4096-bit RSA keys or EC keys
- Add new configuration parameter `aem.ssl_method` for configuring AEM SSL setings [shinesolutions/puppet-aem-curator#220]
- Add JDK11 support for AEM 6.5 [shinesolutions/puppet-aem-curator#220]
- Add new configuration parameter `java.[base_url|filename|version|version_update]` for Java Component
- Add new configuration parameter `aem.[author|publish].jvm_opts` for configuring AEM JVM options
- Add support for NVME Devices [#207]
- Add new configuration parameter to configure EC2 instance type for AMI creation [#207]

### Changed
- Author, Publish & Consolidated installations are now calling the new AEM Java installation manifest in puppet-aem-curator
- Changed default EC2 instance type for AMI creation to `m5.2xlarge` [#207]
- Configuration parameter `aem.jdk` defines the Java version for the AEM Components
- Configuration parameter `java.*` defines the Java version for the Java Components
- Configuration parameters `aem.jdk.[version|version_update]` are deprecated
- Lockdown puppet-agent version to 5.5.21 [#218]
- Lockdown Inspec dependency `parallel` version `1.19.2` [#231]
- Update InSpec tests
- Upgrade `ruby_aem` to 3.10.0 [#218]
- Upgrade `aem_resources` to 7.2.0 [#218]
- Upgrade `aem_curator` to 3.16.0
- Upgrade `puppet` to 5.5.21 [#218]
- Replaced `aco/oracle_java` module with `puppetlabs/java`

### Removed
- Removed alternative command execution from `collectd_jmx` manifest
- Removed deprecated configuration parameters

### Fixed
- Fixed RHEL7 Bash installation script

## 4.26.0 - 2020-06-15
### Changed
- Move AEM SSL Keystore from `crx-quickstart/ssl` to `/etc/ssl` [#209]
- Upgrade ruby_aem to 3.7.0

## 4.25.0 - 2020-05-14
### Changed
- Upgrade ruby_aem to 3.6.0
- Upgrade aem_curator to 3.13.2, aem_resources to 7.0.1

## 4.24.0 - 2020-04-15
### Added
- Add InSpec tests for checking Dispatcher Data Volume
- Add python3 and python2.7 virtualenv
- Add snapshot_users in order to allow destination accounts to copy shared AMIs

### Changed
- Upgrade aem_curator to 3.11.0, aem_resources to 5.5.0

## 4.23.0 - 2020-03-01
### Added
- Add new configuration parameter to enable/disable log configuration for Cloudwatch Agent

### Changed
- Upgrade ruby_aem_aws version to 1.5.0
- Upgrade aem_curator to 3.9.0

## 4.22.0 - 2020-02-09
### Added
- Add feature to enable EBS Volume encryption when baking [#198]
- Add feature to define CMK for enabling EBS Volume encryption [#198]

## 4.21.0 - 2020-01-30
### Changed
- Upgrade aem_curator to 3.8.0

## 4.20.0 - 2020-01-20
### Changed
- Upgrade aem_curator to 3.7.0

## 4.19.0 - 2020-01-08
### Changed
- Change minimum Packer requirement to 1.5.1
- Rename Packer template property temporary_security_group_source_cidr to temporary_security_group_source_cidrs

## 4.18.0 - 2019-12-24
### Added
- Added Dispatcher data volume to CW Metric agent configuration

### Changed
- Upgrade aem_curator to 3.6.0

## 4.17.0 - 2019-12-17
### Changed
- awslogs service is now both disabled and stopped at the end of AMI baking [#192]
- Upgrade aem_curator to 3.5.0, aem_resources to 5.3.0

### Fixed
- Fix AMI baking failure on Amazon Linux 2 due to missing Puppet notify

## 4.16.0 - 2019-12-03
### Added
- Added "zip_url" parameter to CloudWatch Metric in order to customise the `aws-scripts-mon` repository and fix FileSystem value which been passed by it to CloudWatch dashboard.
- Add new configuration properties `aem.jdk.base_url`, `aem.jdk.filename`, `aem.jdk.version`, `aem.jdk.version_update`
- Add new configuration property `aem.dispatcher.ssl_version`
- Add new Data Volume for Author-Dispatcher and Publish-Dispatcher
- Add removal of awslogs service PID file for RHEL & CentOS [#192]

### Changed
- Upgrade aem_curator to 3.3.0, aem_resources to 5.1.0
- Upgrade default JDK to version 8u221
- Upgrade AEM Dispatcher to 4.3.3 using SSL 1.0
- Change default devicemap_root config for rhel7 to xvda
- Increase default root volume size from 20Gb to 30Gb due to more disk space required from adding more tools/software

### Fixed
- Fix missing value for 'aem_healthcheck_version' in hieradata template
- Fix jdk installation path for java alternatives setting
- Fixed dependency for stopping awslogs service [#192]

## 4.15.0 - 2019-10-16
### Added
- Added http, https and file support for archiving certificates

### Changed
- Update private certificate key handling to use same logic as done for the public certificate
- Upgrade aem_curator to 3.0.0
- Upgrade aem_resources to 5.0.0
- Upgrade ruby_aem to 3.4.0

### Removed
- Removed configuration parameter `aws.aem_certs_base`

## 4.14.0 - 2019-10-16
### Changed
- Disabled CloudWatch swap metrics to reduce the metrics in the CW payload
- Remove dispatchers `data-disk` volume from CloudWatch metrics

### Fixed
- Fix missing python-cheetah package for Amazon Linux 2

## 4.13.0 - 2019-10-13
### Added
- Add new RedHat repos rhui-REGION-rhel-server-extras and rhel-7-server-rhui-optional-rpms to support the latest package availability changes [#182]

## 4.12.0 - 2019-09-20
### Added
- Add new `cloudwatch log to s3` cronjob logfile to Cloudwatch config

## 4.11.1 - 2019-09-12
### Fixed
- Fix Author-Publish-Dispatcher application role criteria

## 4.11.0 - 2019-09-10
### Added
- Add version filter env var support to make ami-ids target
- Add CloudWatch metric agent installation support

## 4.10.0 - 2019-08-19
### Added
- Add InSpec test to verify JDK keystore password is not the infamous `changeit` [#131]

## 4.9.0 - 2019-08-16
### Added
- Add AWS resources creation and deletion to integration testing
- Add encryption to AWS resources S3 bucket
- Add Packer AEM version as AWS resources tag including created AMI
- Add config property aws.temporary_security_group_source_cidr

### Changed
- Upgrade ruby_aem_aws version to 1.4.0

### Removed
- Removed bundler gem installation

### Fixed
- Fixed hiera SSM Parameterstore lookup for keystore password

## 4.8.0 - 2019-08-06
### Added
- Add new log resources for AWS Cloudwatch [shinesolutions/aem-aws-stack-builder#298]

### Changed
- Upgrade aem_curator to 2.7.0
- Update config hiera data files to contain a list of packages to install on OS
- Updated process of config module to install packages.

### Removed
- Remove Development Tools OS packages installation, replaced with autoconf, automake, libtool [#112]
- Remove old ServerSpec and nokogiri dependencies which require native compilation

### Fixed
- Fix aws.ami_users configuration property description to describe data format [#162]

## 4.7.0 - 2019-07-24
### Changed
- Upgrade aem_curator to 2.6.0
- Upgrade aem_resources to 4.1.0
- Upgrade default aem_profile to aem65_sp1

### Removed
- Remove aem.start_opts configuration support following upgrade to puppet-aem 3.0.0

## 4.6.0 - 2019-07-02
### Changed
- Upgrade aem_curator to 2.3.0
- Set /opt/shinesolutions base dir permission to 755

### Fixed
- Fix missing region parameter for SSM parameter store provisioning

## 4.5.0 - 2019-06-15
### Changed
- Upgrade aem_curator to 2.0.0
- Upgrade aem_resources to 4.0.0
- Upgrade ruby_aem to 3.2.1

## 4.4.1 - 2019-05-24
### Changed
- Revert hiera_ssm_paramstore setting to not enforce prefix and to not pre-load all parameters

### Fixed
- Fix SSM parameters support for name with leading slash

## 4.4.0 - 2019-05-23
### Changed
- Upgrade default aem.profile to aem64_sp4
- Upgrade aem_curator to 1.25.0
- Modify AEM license and AEM Java Keystore password to be SSM secure string parameter

## 4.3.0 - 2019-05-21
### Changed
- Upgrade aem_curator to 1.22.1

## 4.1.0 - 2019-04-18
### Added
- Add aem.author.run_modes and aem.publish.run_modes configuration properties

### Changed
- Upgrade aem_curator to 1.22.0
- Upgrade aem_resources to 3.10.0

## 4.0.0 - 2019-04-07
### Added
- Add support for CIS hardened source AMI
- Add JDK keystore password and TLS private key resource provisioning to aws-resources CF stack [#124] [#126]
- Add new configuration property aem.dispatcher.apache_module_base_url
- Add new configuration property aws.resource.create_iam_packer_role

### Changed
- Changed hiera parameters for repository volume to data volume
- Upgrade aem_curator to 1.19.0
- Upgrade aem_resources to 3.9.0
- Ensure crx-quickstart/install directory is empty only after AEM is stopped
- AEM Java keystore should be owned by AEM service user [#129]

### Fixed
- Fix AEM install directory clean up at the end of AEM provisioning phase [#78]
- Fix repository volume device hieradata configuration to consume user config and handle component-specific config [#127]

## 3.7.0 - 2019-02-17
### Added
- Add support for managing AWS resources in CloudFormation stack

### Changed
- Update Apache Dispatcher Module version to 4.3.2 from 4.3.1
- Upgrade aem_curator to 1.10.0
- Upgrade aem_resources to 3.8.0 aem_curator to 1.11.0

## 3.6.0 - 2019-02-04
### Changed
- Upgrade aem_resources to 3.6.0, aem_curator to 1.9.1
- Upgrade ruby_aem to 2.5.1

## 3.5.0 - 2019-01-31
### Added
- Parameter for defining aem healthcheck version
- Add platform_type fact to hieradata for configuring repository volume setup
- Create s3 bucket during packer instance profile creation using CFN to store AEM artifacts

### Changed
- Update default Dispatcher download URL [#103]
- Update Apache Dispatcher Module version to 4.3.1
- Upgrade aem_resources to 3.5.0, aem_curator to 1.7.0
- Upgrade default AEM profile to aem64_sp3
- Upgrade ruby_aem to 2.4.0
- Lock down bundler on host gem to version 1.17.3 in order to support Ruby older than 2.3.0
- Modified TLS private key to download from AWS Secrets Manager or S3 as a fallback
- Move AEM license storage from S3 to AWS Systems Manager Parameter Store secure string

### Removed
- Hiera config parameter duplications

### Fixed
- InSpec awslogs service enabled and running test [#60]
- InSpec cq.pid file not exists test [#60]

## 3.4.2 - 2018-12-12
### Changed
- Update OS base package installation
- Add os base package bind-utils
- Add JSON, YAML, Python, and Rubocop checks to lint target
- Change changelog format to adhere keep-a-changelog standard

### Removed
- Move examples user config to https://github.com/shinesolutions/aem-helloworld-config

## 3.4.1 - 2018-12-05
### Added
- Add component check to test for ruby library version [#99]

### Changed
- Fixed AEM Keystore path for component tests
- Extend component test to verify AEM Keystore contains the imported key [#95]
- Upgrade ruby_aem to 2.2.1 for https truststore config fix

## 3.4.0 - 2018-11-28
### Changed
- Move TLS certificate storage from S3 to AWS Certificate Manager [#41]
- Move TLS certificate's private key storage from S3 to AWS Secrets Manager [#47]
- Upgrade puppet-amazon-ssm-agent to 0.9.3
- Upgrade puppet-aem-curator to 1.3.0
- Upgrade puppet-aem-resources to 3.3.0
- Upgrade ruby_aem to 2.2.0 for SAML support

## 3.3.0 - 2018-10-22
### Added
- Add tomcat service installation for java component [#89]

### Changed
- Upgrade puppet-aem-resources to 3.2.1, puppet-aem-curator to 1.2.3
- Upgrade example config AEM profile for AEM 6.4 to aem64_sp2
- Increase post AEM stop delay to 5 minutes, to match service post stop timeout
- Add InSpec check to ensure cq.pid doesn't exist on author, publish, author-publish-dispatcher components
- Fix Puppet installation error due to renamed rpm URL
- Upgrade puppet-aem-resources to 3.2.0, puppet-aem-curator to 1.2.2

### Removed
- Move Puppet AEM resource stopped status check from Packer templates to puppet-aem-curator

## 3.2.0 - 2018-09-12
### Added
- Add CloudWatch config for SSM commands offline-snapshot
- Add CloudWatch config for SSM commands offline-compaction-snapshot
- Add CloudWatch config for SSM commands manage-service
- Add CloudWatch config for SSM commands wait-until-ready

### Changed
- Update Cloudwatch config date format for cloud init logfile
- Modify proxy setting config file for CloudWatch to /var/awslogs/etc/proxy.conf
- Lock down awscli version to 1.16.10 let it determine boto dependencies when awscli installation is enabled
- Lock down boto3 to 1.8.5

### Removed
- Remove AMI ID variable file support

## 3.1.0 - 2018-08-10
### Added
- Add AEM Hello World Custom Image Provisioner to integration test [#79]
- Add new configuration custom_image_provisioner.pre.timeout and custom_image_provisioner.post.timeout

### Changed
- Upgrade ruby_aem to 2.1.0
- Upgrade aem_curator and aem_resources to support new system users provisioning

## 3.0.1 - 2018-07-11
### Added
- Add Custom Image Provisioner pre and post steps support [#77]

### Changed
- Upgrade example config AEM profiles to aem62_sp1_cfp15, aem63_sp2_cfp2, and aem64_sp1
- Upgrade ruby_aem_aws to 1.2.0

## 3.0.0 - 2018-07-07
### Changed
- Upgrade ruby_aem to 2.0.0, puppet-aem-resources to 3.0.0, and puppet-aem-curator to 1.0.0 for AEM 6.4 support

## 2.8.0 - 2018-06-27
### Added
- Add CloudWatch config for content health check cron log

## 2.7.3 - 2018-06-20
### Changed
- Upgrade ruby_aem_aws to 1.1.0
- Lock down nokogiri to 1.8.2 due to additional package dependencies in 1.8.3

## 2.7.2 - 2018-06-01
### Changed
- Upgrade ruby_aem_aws to 1.0.0

## 2.7.1 - 2018-05-31
### Added
- Add support for AEM 6.3 SP2 CFP1 AMI baking

### Removed
- Move CodeBuild and CodePipeline support to aem-platform-ci repo

## 2.7.0 - 2018-05-10
### Added
- Add AEM start options support
- Initial experimental effort to support Docker platform type

### Changed
- Rename all component targets to platform-component targets
- Fix aws-cli and CloudWatch logs config flags conditional check

## 2.6.0 - 2018-04-24
### Added
- Add InSpec AEM testing support
- Add support to create AMIs on AWS CodeBuild and CodePipeline
- Add support for AEM 6.4 AMI baking

### Changed
- Increase minimum Ansible version requirement to 2.5.0

## 2.5.0 - 2018-04-10
### Added
- Add config-examples-- make targets
- Add CloudWatch logging for Dispatchers (Author and Publish), Orchestrator and Chaos Monkey
- Add platform_type configuration [#71]
- Add aws.root_volume_size and aws.data_volume_size configurations [#69]

### Changed
- Fix SSM agent proxy configuration support
- Set Ansible config hash behaviour to merge
- Replace Stack Builder AMI IDs config generation Python script with Ansible module

## 2.4.0 - 2018-03-04
### Added
- Explicit installation of libtool, autoconf, and automake for native package compilation
- Add CentOS OS type support [#65]
- Add OS Type system tag
- Add aws.install_ssm_agent configuration

## 2.3.2 - 2018-02-05
### Changed
- Fix Cumulative Fix Pack support due to new naming convention in AEM 6.3 for CFPs

### Removed
- Remove lint and validate dependency from Makefile package target [#63]
- Move Collectd configuration from packer-aem to aem-aws-stack-provisioner

## 2.3.1 - 2018-01-31
### Added
- Add support for AEM 6.3 SP1 CFP2

## 2.3.0 - 2018-01-29
### Added
- Add no_proxy, aws.vpc_id, and aws.subnet_id configurations

### Changed
- Enabled installation of Amazon SSM Agent by default
- Fixed cloud_writer.py. Added third argument while loading Flusher module [#58]
- Upgrade ruby_aem to 1.4.1 for nokogiri security vulnerability fix

## 2.2.0 - 2018-01-05
### Added
- Add Application Profile system tag [#53]
- Add OS type configuration support [#54]
- Add AEM Dispatcher version configuration
- Add Ansible module packer_tags for adding custom tags to Packer templates
- Add AEM Dispatcher listen ports testing
- Introduce generic YAML configuration using Ansible [#52]

### Changed
- Replace Serverspec with InSpec for testing [#42]
- Fix AEM Dispatcher not listening on port 443

## 2.1.0 - 2017-11-29
### Added
- Added AuthorPublishDispatcher component
- Added RHEL 7.x support
- Introduce component-specific Packer config [#44]
- Add Packer user variables for http_proxy, https_proxy, and no_proxy [#45]
- Add setconfig.sh script to specify hieradata and packer customisation

### Changed
- Service names are now 'aem-author' (AEM Author) and 'aem-publish' (AEM Publish), previously 'aem-aem'
- Replace default https port for author component from 5433 to 5432
- Replace librarian-puppet with r10k for Puppet dependency management
- Replace AEM-specific provisioning manifests with puppet-aem-curator [#35]
- AEM base is owned by root, AEM installation directory is owned by aem-<aem_id> user
- Remove NewRelic as this should be a customisation [#38]
- Tags Cost Center, Availability, Owner are no longer included by default [#37]
- Volumes created during AMI baking are now tagged via run_volume_tags [#50]
- Upgrade ruby_aem to 1.4.0
- Upgrade Puppet to version 5
- Default ami_var_file is stage/ami-ids.json
- ami_var_file no longer update source_ami and remove underscore ami postfix
- Stack Builder-specific AMI IDs config script file is now named scripts/create-stack-builder-ami-ids-config.py
- Fix intermittent AEM installation error 500 loop

## 1.1.0 - 2017-06-02
### Changed
- Upgrade AEM Cumulative Fix Pack to SP1-CFP3
- Update to Java Version 8u131
- Update puppet module aco-oracle_java - support Java '8u131'
- Upgrade ruby_aem to 1.3.0

## 1.0.0 - 2019-05-21
### Added
- Add aem65 to to ami-ids-examples make target

### Changed
- Upgrade aem_curator to 1.24.1
- Upgrade aem_resources to 3.10.1
- Upgrade amazon_ssm_agent to 0.9.4
- Upgrade ruby_aem_aws to 1.2.1
- Upgrade aem-helloworld-custom-image-provisioner to 0.9.1

## 1.0.0 - 2017-05-22
### Added
- Initial version
