# Change logs for Rudder 4.1.\* versions

Rudder 4.1 is currently the beta version of Rudder.

This page provides a summary of changes for each version. Previous beta
and rc versions are listed below for convenience.

**Main new features in Rudder 4.1:**

  - Organize Rules and Directives by setting key=value tags (using UI or REST API)
  - Add or remove Node properties directly in the web interface
  - Share files between Nodes (via new generic methods)
  - Trigger agent runs on Nodes via relay servers without modifying your network configuration
  - Many Techniques renamed to be more explicit and now displayed in alphabetical order to make finding them easier
  - Customize Rudder behavior with the new hook system based on server-side actions
  - Improved user experience, overall improvement of web performance (web resources are cached), many minor UI tweaks  (page titles, forms, buttons, filters, ...)
  - Switched to a new graph rendering library, fixing all performance issues with Firefox
  - Agent package now embeds OpenSSL on unmaintained Debian/Ubuntu distributions (Debian 5, Debian 6, Ubuntu 12.04, Ubuntu 12.10) as well as unmaintained RHEL/SLES distributions.
  - New plugin packaging system for easier plugin management
  - New plugin ‘data sources’: Automatically import Node properties from external REST APIs

**Installing, upgrading and testing**

  - Install docs:
    https://www.rudder-project.org/doc-4.1/_install_rudder_server.html
  - Upgrade docs:
    https://www.rudder-project.org/doc-4.1/_upgrade_rudder.html
  - Download links: https://www.rudder-project.org/site/get-rudder/downloads/

We also recommend using the [Rudder
Vagrant](https://github.com/Normation/rudder-vagrant) config if you want
a quick and easy way to get an installation for testing.

**Operating systems supported**

This version provides packages for these operating systems:

  - Rudder server and Rudder relay: **Debian 7, Debian 8, RHEL/CentOS 6, RHEL/CentOS 7
    (64 bits), SLES 11, SLES 12, Ubuntu 14.04, Ubuntu 16.04**
  - Rudder agent: all of the above plus **Debian 5, Debian 6,
    RHEL/CentOS 3, RHEL/CentOS 5, CentOS 7 (32 bits), Fedora 18, SLES
    10, SLES 12, Ubuntu 10.04, Ubuntu 12.04, Ubuntu 12.10**
  - Rudder agent (binary packages available from
    ([Normation](http://www.normation.com)): **Windows Server 2008-2012,
    AIX 5-6-7**

**Note**: As of Rudder 4.1, the rudder-agent-thin and rudder-server-relay packges are
no longer available in Debian 5, Debian 6, Ubuntu 10.04, Ubuntu 12.10, Fedora 18, 
RHEL/CentOS 3 and RHEL/CentOS 5


## Rudder 4.1.0 (2017-03-30)

### Changes

#### API

  - Remote run API should use relay API
    ([\#9714](https://www.rudder-project.org/redmine/issues/9714))
  - Deprecate API v5, v6 and v7, and remove API v2,3,4
    ([\#9836](https://www.rudder-project.org/redmine/issues/9836))

#### Web - UI & UX

  - Add icon for directives which can be migrated to an upper technique version
    ([\#10421](https://www.rudder-project.org/redmine/issues/10421))
  - Add icon for directives which use deprecated technique
    ([\#10420](https://www.rudder-project.org/redmine/issues/10420))
  - Find a way to display "deprecated" techniques which still contain directives in the directives tree
    ([\#10229](https://www.rudder-project.org/redmine/issues/10229))
  - Fix some details in Directives page
    ([\#10384](https://www.rudder-project.org/redmine/issues/10384))
  - Group Type order should be switched
    ([\#10330](https://www.rudder-project.org/redmine/issues/10330))
  - Adjust providers display in the node properties tab
    ([\#10320](https://www.rudder-project.org/redmine/issues/10320))
  - Display provider of node properties if defined
    ([\#10302](https://www.rudder-project.org/redmine/issues/10302))
  - Change graph lib to more efficent one
    ([\#8171](https://www.rudder-project.org/redmine/issues/8171))
  - Adjust the height box height's css property instead of max-height 
    ([\#10252](https://www.rudder-project.org/redmine/issues/10252))
  - Add autocomplete on rule/directive tags
    ([\#10192](https://www.rudder-project.org/redmine/issues/10192))
  - The "Technique version" select and "Migrate" button should be aligned
    ([\#9938](https://www.rudder-project.org/redmine/issues/9938))
  - Reorder and hide deprecated Techniques in Directive tree 
    ([\#10228](https://www.rudder-project.org/redmine/issues/10228))
  - UI to define node properties
    ([\#10169](https://www.rudder-project.org/redmine/issues/10169))
  - Reorganize Directives page interface
    ([\#10080](https://www.rudder-project.org/redmine/issues/10080))
  - Reorganize Rules page interface
    ([\#9960](https://www.rudder-project.org/redmine/issues/9960))
  - Improve Json display in the Nodes properties tab
    ([\#9984](https://www.rudder-project.org/redmine/issues/9984))

#### Web - Config management

  - Remove all datasource code from Rudder main and add needed hooks
    ([\#10050](https://www.rudder-project.org/redmine/issues/10050))

#### Architecture - Internal libs

  - Change pom version on master to 4.1
    ([\#9686](https://www.rudder-project.org/redmine/issues/9686))

#### Documentation

  - Document how to build an agent
    ([\#10333](https://www.rudder-project.org/redmine/issues/10333))
  - Change page split level and reorganize sections
    ([\#10350](https://www.rudder-project.org/redmine/issues/10350))
  - Document usage of file sharing between nodes
    ([\#10278](https://www.rudder-project.org/redmine/issues/10278))
  - Add guideline for technique naming
    ([\#10222](https://www.rudder-project.org/redmine/issues/10222))
  - Use the lato font in the manual
    ([\#9945](https://www.rudder-project.org/redmine/issues/9945))
  - Document the relay API
    ([\#9997](https://www.rudder-project.org/redmine/issues/9997))
  - Prepare manual for 4.1
    ([\#9887](https://www.rudder-project.org/redmine/issues/9887))
  - Change doc title for 4.1
    ([\#9753](https://www.rudder-project.org/redmine/issues/9753))

#### Miscellaneous

  - Add a convention for ".disabled" hooks to not be executed
    ([\#10412](https://www.rudder-project.org/redmine/issues/10412))

#### Agent

  - Create a cfengine_rudder class
    ([\#9384](https://www.rudder-project.org/redmine/issues/9384))
  - Extend rudder-sign to add new information
    ([\#9996](https://www.rudder-project.org/redmine/issues/9996))
  - Improve usage of ncf logging in rudder command
    ([\#9280](https://www.rudder-project.org/redmine/issues/9280))
  - Warn the user if rudder agent is not run as root
    ([\#9684](https://www.rudder-project.org/redmine/issues/9684))

#### Packaging

  - rpm packages should depend on java headless
    ([\#10468](https://www.rudder-project.org/redmine/issues/10468))
  - Registered Plugins should be kept at upgrade
    ([\#10251](https://www.rudder-project.org/redmine/issues/10251))
  - Stop jetty before upgrading the webapp
    ([\#9820](https://www.rudder-project.org/redmine/issues/9820))
  - Embed openssl on old debian systems
    ([\#10303](https://www.rudder-project.org/redmine/issues/10303))
  - Upgrade OpenSSL to 1.0.2k
    ([\#10246](https://www.rudder-project.org/redmine/issues/10246))
  - Upgrade fusion agent to 2.3.19
    ([\#9763](https://www.rudder-project.org/redmine/issues/9763))
  - Redirect http to https in relay api
    ([\#10073](https://www.rudder-project.org/redmine/issues/10073))
  - Permit skipping scala build within packages
    ([\#10055](https://www.rudder-project.org/redmine/issues/10055))
  - use suse_version instead of sles_version during build
    ([\#9919](https://www.rudder-project.org/redmine/issues/9919))
  - ncf-api-venv user should not have access to a shell
    ([\#9993](https://www.rudder-project.org/redmine/issues/9993))
  - Build slapd with lmdb
    ([\#9839](https://www.rudder-project.org/redmine/issues/9839))
  - Upgrade CFEngine in Rudder agent to 3.10
    ([\#9737](https://www.rudder-project.org/redmine/issues/9737))
  - Automatically set year in Rudder interface at build time
    ([\#9891](https://www.rudder-project.org/redmine/issues/9891))

#### Initial promises & sys tech

  - Remove unused body yum_remi
    ([\#10349](https://www.rudder-project.org/redmine/issues/10349))
  - Use rudder agent run as cfruncommand
    ([\#10081](https://www.rudder-project.org/redmine/issues/10081))

#### System integration

  - Add a package manager for plugins
    ([\#10254](https://www.rudder-project.org/redmine/issues/10254))
  - Do not create a temporary cron a postinstall
    ([\#9860](https://www.rudder-project.org/redmine/issues/9860))

#### Architecture - Dependencies

  -  Requires Java8 (jdk8) for Rudder 4.1
    ([\#9917](https://www.rudder-project.org/redmine/issues/9917))
  - Switch to Scala 2.12 / Lift 3.0 
    ([\#10127](https://www.rudder-project.org/redmine/issues/10127))

#### Performance and scalability

  - Add caching information to static JS/CSS resources
    ([\#4519](https://www.rudder-project.org/redmine/issues/4519))

#### Architecture - Refactoring

  - Add a database table for node compliance 
    ([\#9645](https://www.rudder-project.org/redmine/issues/9645))
  - Scala actors are deprecated in scala 2.11 and removed in 2.12: update inventory-endpoint
    ([\#10119](https://www.rudder-project.org/redmine/issues/10119))

#### Server components

  - Implement notifications for different server-side actions and events (hooks)
    ([\#8353](https://www.rudder-project.org/redmine/issues/8353))

#### Techniques

  - More consistant naming of techniques
    ([\#10214](https://www.rudder-project.org/redmine/issues/10214))
  - Deprecate old techniques versions
    ([\#10159](https://www.rudder-project.org/redmine/issues/10159))

### Bug fixes

#### API

  - Fixed: Allow relay-api to make asynchronous remote run call with output 
    ([\#10114](https://www.rudder-project.org/redmine/issues/10114))
  - Fixed: API compatibility feature switch must be removed in 4.1
    ([\#10322](https://www.rudder-project.org/redmine/issues/10322))
  - Fixed: Log an error when Rest API fails 
    ([\#10295](https://www.rudder-project.org/redmine/issues/10295))
  - Fixed: Missing timezone information in API "node details"
    ([\#10280](https://www.rudder-project.org/redmine/issues/10280))
  - Fixed: Fix behavior of directive API and make api more consistent
    ([\#10225](https://www.rudder-project.org/redmine/issues/10225))

#### Web - UI & UX

  - Fixed: "New category" button hides "Categories" title on small screens
    ([\#10510](https://www.rudder-project.org/redmine/issues/10510))
  - Fixed: Some tooltips can't overflow their container
    ([\#10509](https://www.rudder-project.org/redmine/issues/10509))
  - Fixed: A running Policy generation is not displayed on the Status dropdown
    ([\#10451](https://www.rudder-project.org/redmine/issues/10451))
  - Fixed: Directive page not displaying with "None.get" in logs
    ([\#10501](https://www.rudder-project.org/redmine/issues/10501))
  - Fixed: When activating change requests, the CR zone doesn't appear in the main bar
    ([\#10499](https://www.rudder-project.org/redmine/issues/10499))
  - Fixed: GUI breaks completely with IE 11
    ([\#10452](https://www.rudder-project.org/redmine/issues/10452))
  - Fixed: padding-down instead of padding-bottom in rudder.css
    ([\#10465](https://www.rudder-project.org/redmine/issues/10465))
  - Fixed: Weird appearance of accet new nodes popup
    ([\#10458](https://www.rudder-project.org/redmine/issues/10458))
  - Fixed: Display issue on "Accept new Nodes" page
    ([\#9165](https://www.rudder-project.org/redmine/issues/9165))
  - Fixed: Dropdown lists in directive forms are not wide enough and hide the contents of options
    ([\#10361](https://www.rudder-project.org/redmine/issues/10361))
  - Fixed: In the rule table, Recent changes column change size during page loading
    ([\#10340](https://www.rudder-project.org/redmine/issues/10340))
  - Fixed: On the Rule details, if I click on "Clone", then cancel action, I get switched to Settings tab
    ([\#10345](https://www.rudder-project.org/redmine/issues/10345))
  - Fixed: Directive from a whole deprecated technique are not displayed
    ([\#10422](https://www.rudder-project.org/redmine/issues/10422))
  - Fixed: "Create with latest version" button text is cut off in new directive page
    ([\#10358](https://www.rudder-project.org/redmine/issues/10358))
  - Fixed: Cannot use slashes in quick search
    ([\#10407](https://www.rudder-project.org/redmine/issues/10407))
  - Fixed: Quick search text has gone a hard to read gray
    ([\#10400](https://www.rudder-project.org/redmine/issues/10400))
  - Fixed: Checkboxes in Administration menu are not locked for users with missing permissions
    ([\#9328](https://www.rudder-project.org/redmine/issues/9328))
  - Fixed: Bad Rudder logo in src/main/webapp/images
    ([\#10386](https://www.rudder-project.org/redmine/issues/10386))
  - Fixed: Rudder (svg) logo aren't displayed with chrome 
    ([\#10387](https://www.rudder-project.org/redmine/issues/10387))
  - Fixed: Tooltips are broken in Rule tables
    ([\#10389](https://www.rudder-project.org/redmine/issues/10389))
  - Fixed: Directive "Migrate" button is stuck to the version dropdown list
    ([\#10360](https://www.rudder-project.org/redmine/issues/10360))
  - Fixed: "Delete <component> #1" button in directive form's text is not centered
    ([\#10359](https://www.rudder-project.org/redmine/issues/10359))
  - Fixed: Save button shown even no permission to change it
    ([\#9819](https://www.rudder-project.org/redmine/issues/9819))
  - Fixed: If there is an error in the Parameter edition/creation popup, its shape change
    ([\#10248](https://www.rudder-project.org/redmine/issues/10248))
  - Fixed: Inconsistent capitalization of titles in the menu
    ([\#9545](https://www.rudder-project.org/redmine/issues/9545))
  - Fixed: Inconsistent message style in settings page
    ([\#9426](https://www.rudder-project.org/redmine/issues/9426))
  - Fixed: Wrong action named in API accounts table
    ([\#10203](https://www.rudder-project.org/redmine/issues/10203))
  - Fixed: Compliance display when hoverving over the compliance bar is too precise
    ([\#9323](https://www.rudder-project.org/redmine/issues/9323))
  - Fixed: Compliance/Recent change column should not be present by default in directive screen
    ([\#10339](https://www.rudder-project.org/redmine/issues/10339))
  - Fixed: Compliance bar isn't display the same way in 'List nodes' and 'Rules' pages
    ([\#10321](https://www.rudder-project.org/redmine/issues/10321))
  - Fixed: Display of shared files popup is broken
    ([\#10329](https://www.rudder-project.org/redmine/issues/10329))
  - Fixed: Unconsistent titles style in Rule settings
    ([\#10325](https://www.rudder-project.org/redmine/issues/10325))
  - Fixed: Disabled label disappear passing the mouse over the policy mode label
    ([\#10323](https://www.rudder-project.org/redmine/issues/10323))
  - Fixed: Cannot change schedule on Node 
    ([\#10318](https://www.rudder-project.org/redmine/issues/10318))
  - Fixed: Clone group popup is broken
    ([\#10307](https://www.rudder-project.org/redmine/issues/10307))
  - Fixed: Lost space at the bottom of the group page
    ([\#10281](https://www.rudder-project.org/redmine/issues/10281))
  - Fixed: When clicking refresh in rules, grid header height change
    ([\#10262](https://www.rudder-project.org/redmine/issues/10262))
  - Fixed: When trying to create a new API account that has the same name as an existing acocunt, nothing happen
    ([\#10250](https://www.rudder-project.org/redmine/issues/10250))
  - Fixed: Setting title are barelly outstanding
    ([\#10261](https://www.rudder-project.org/redmine/issues/10261))
  - Fixed: Button are not correctly aligned compared to tables in 4.1
    ([\#10257](https://www.rudder-project.org/redmine/issues/10257))
  - Fixed: Rules form fields are too wide
    ([\#10202](https://www.rudder-project.org/redmine/issues/10202))
  - Fixed: Vertically center the filter line in the event logs page
    ([\#10219](https://www.rudder-project.org/redmine/issues/10219))
  - Fixed: Unconsistent titles style in the Settings page
    ([\#10217](https://www.rudder-project.org/redmine/issues/10217))
  - Fixed: Parameters description won't show up in 4.1
    ([\#10197](https://www.rudder-project.org/redmine/issues/10197))
  - Fixed: Broken display in Rule popup creation
    ([\#10182](https://www.rudder-project.org/redmine/issues/10182))
  - Fixed: If we set a short description for a Rule, it won't show up anymore in the rule list
    ([\#10196](https://www.rudder-project.org/redmine/issues/10196))
  - Fixed: On Group creation, the tooltip on the "Save" button doesn't appear when it is disabled
    ([\#10116](https://www.rudder-project.org/redmine/issues/10116))
  - Fixed: Broken text fields in directive form
    ([\#10164](https://www.rudder-project.org/redmine/issues/10164))
  - Fixed: Nothing happens when trying to save a Directive
    ([\#9948](https://www.rudder-project.org/redmine/issues/9948))
  - Fixed: Put in bold rule form's required fields label
    ([\#9949](https://www.rudder-project.org/redmine/issues/9949))
  - Fixed: Put in bold "Technique version" label
    ([\#9935](https://www.rudder-project.org/redmine/issues/9935))

#### Documentation

  - Fixed: Inconsistent section order
    ([\#10413](https://www.rudder-project.org/redmine/issues/10413))
  - Fixed: Remove doc for the old quicksearch bar that has been removed
    ([\#10401](https://www.rudder-project.org/redmine/issues/10401))
  - Fixed: Doc about copying ncf technique to /var/rudder/ncf/local is false
    ([\#10269](https://www.rudder-project.org/redmine/issues/10269))
  - Fixed: Broken formatting of plugin packaging doc
    ([\#10297](https://www.rudder-project.org/redmine/issues/10297))
  - Fixed: We should disable link tests for the manual on master 
    ([\#9803](https://www.rudder-project.org/redmine/issues/9803))

#### Web - Maintenance

  - Fixed: There is no error logged when an error occurs when updating information of Node in Node cache
    ([\#10290](https://www.rudder-project.org/redmine/issues/10290))

#### Web - Technique editor

  - Fixed: Cannot open technique editor on SLES12
    ([\#10511](https://www.rudder-project.org/redmine/issues/10511))

#### Web - Nodes & inventories

  - Fixed: On Group page, we can click on "Save" on arrival on the page, and it prevent any further saving of the Group
    ([\#10376](https://www.rudder-project.org/redmine/issues/10376))
  - Fixed: No error message in group creation popup if no name is set
    ([\#10328](https://www.rudder-project.org/redmine/issues/10328))
  - Fixed: Include Timezone in Node Info
    ([\#7092](https://www.rudder-project.org/redmine/issues/7092))
  - Fixed: Improve management of rights and other metadata of node properties
    ([\#10235](https://www.rudder-project.org/redmine/issues/10235))
  - Fixed: Cannot choose between Group or category when creating a Group
    ([\#10249](https://www.rudder-project.org/redmine/issues/10249))
  - Fixed: Can not see details of pending node
    ([\#10174](https://www.rudder-project.org/redmine/issues/10174))

#### Web - Config management

  - Fixed: No generation triggered at the end of installation
    ([\#10448](https://www.rudder-project.org/redmine/issues/10448))
  - Fixed: When upgrading to 4.1, rudder.community.checkpromises.command=/bin/true option is lost 
    ([\#10379](https://www.rudder-project.org/redmine/issues/10379))
  - Fixed: Dataource can not override an existing property
    ([\#10520](https://www.rudder-project.org/redmine/issues/10520))
  - Fixed: Policy validation fails
    ([\#10446](https://www.rudder-project.org/redmine/issues/10446))
  - Fixed: Remove "rights" in node property
    ([\#10301](https://www.rudder-project.org/redmine/issues/10301))
  - Fixed: When we filter directive by tags, and update a directive, the tree is refreshed without taking into account the filter
    ([\#10271](https://www.rudder-project.org/redmine/issues/10271))
  - Fixed: When we add/remove/update a tag to a Directive/Rule, we get an empty event log
    ([\#10275](https://www.rudder-project.org/redmine/issues/10275))
  - Fixed: Tag filter creation greyed out after creating a tag filter
    ([\#10272](https://www.rudder-project.org/redmine/issues/10272))
  - Fixed: Renable WriteSystemTechniquesTest
    ([\#10150](https://www.rudder-project.org/redmine/issues/10150))
  - Fixed: When I save a Directive, after cliking "save", it's not possible to scroll anymore in the Directive tree
    ([\#10010](https://www.rudder-project.org/redmine/issues/10010))
  - Fixed: Rule details text can be misleading
    ([\#6143](https://www.rudder-project.org/redmine/issues/6143))

#### Miscellaneous

  - Fixed: Error when putting uuid.hive in inventory-updates
    ([\#10070](https://www.rudder-project.org/redmine/issues/10070))
  - Fixed: Validation hooks should execute cf-promises by exec
    ([\#10449](https://www.rudder-project.org/redmine/issues/10449))
  - Fixed: Clean tags data model 
    ([\#9934](https://www.rudder-project.org/redmine/issues/9934))
  - Fixed: Promise validation errors (cf-promises) are unreadable
    ([\#10175](https://www.rudder-project.org/redmine/issues/10175))

#### Agent

  - Fixed: Scary message about OpenSSL on SLES when running rudder agent update
    ([\#10066](https://www.rudder-project.org/redmine/issues/10066))
  - Fixed: Some QEMU virtual machines are seen as physical
    ([\#9616](https://www.rudder-project.org/redmine/issues/9616))
  - Fixed: If rudder server component is stopped on Rudder root server, it is never restarted
    ([\#10258](https://www.rudder-project.org/redmine/issues/10258))

#### Packaging

  - Fixed: slapd migration for 4.1 is not done on Ubuntu 16.04
    ([\#10517](https://www.rudder-project.org/redmine/issues/10517))
  - Fixed: Rudder 4.1 fails to install Ubuntu/Debian because of rudder-slapd service restart
    ([\#10506](https://www.rudder-project.org/redmine/issues/10506))
  - Fixed: Error when upgrading from Rudder 3.1 to Rudder 4.1 on Debian 8
    ([\#10440](https://www.rudder-project.org/redmine/issues/10440))
  - Fixed: On SLES12, missing package rsyslog-module-pgsql
    ([\#10497](https://www.rudder-project.org/redmine/issues/10497))
  - Fixed: Use the same initial database password everywhere to avoid breaking database connection before rudder-init
    ([\#10484](https://www.rudder-project.org/redmine/issues/10484))
  - Fixed: Relay-Api does not handle different Apache versions
    ([\#10455](https://www.rudder-project.org/redmine/issues/10455))
  - Fixed: Error on hooks on fresh install on Centos7
    ([\#10436](https://www.rudder-project.org/redmine/issues/10436))
  - Fixed: LDAP error at upgrade - Cannot allocate memory
    ([\#10424](https://www.rudder-project.org/redmine/issues/10424))
  - Fixed: On Centos 7.3, upgrading from 4.0 to 4.1 fail due to SELinux problem
    ([\#10372](https://www.rudder-project.org/redmine/issues/10372))
  - Fixed: Upgrading from 4.0 to 4.1 failed on Centos7.3, and purged LDAP directory
    ([\#10373](https://www.rudder-project.org/redmine/issues/10373))
  - Fixed: Don't display warning about configuring policy server on root server
    ([\#8976](https://www.rudder-project.org/redmine/issues/8976))
  - Fixed: make clean in rudder agent package doesn't remove build-cfengine-stamp
    ([\#10334](https://www.rudder-project.org/redmine/issues/10334))
  - Fixed: Accept TTL with spaces in relay API
    ([\#10296](https://www.rudder-project.org/redmine/issues/10296))
  - Fixed: Error downloading perl modules with https
    ([\#10264](https://www.rudder-project.org/redmine/issues/10264))
  - Fixed: Missing prefix in asynchronous output in remote run
    ([\#10190](https://www.rudder-project.org/redmine/issues/10190))
  - Fixed: Impossible to share file due to wrong permissions for /var/rudder/shared-files
    ([\#10184](https://www.rudder-project.org/redmine/issues/10184))
  - Fixed: the shared-files directory is owned by root
    ([\#10178](https://www.rudder-project.org/redmine/issues/10178))
  - Fixed: openjdk8 cannot be installed if there is a backport in the building os
    ([\#10163](https://www.rudder-project.org/redmine/issues/10163))
  - Fixed: Missing entry in rudder-web.properties after update to 4.1.0.b2
    ([\#10132](https://www.rudder-project.org/redmine/issues/10132))
  - Fixed: rudder-relay has bad "sed" line
    ([\#10131](https://www.rudder-project.org/redmine/issues/10131))
  - Fixed: The user trying to open nodes list in relay-api is not rudder
    ([\#10068](https://www.rudder-project.org/redmine/issues/10068))
  - Fixed: Wrong ncf version dependency in 4.1
    ([\#10091](https://www.rudder-project.org/redmine/issues/10091))
  - Fixed: On CentOS relay API uses /etc/httpd/logs/wsgi.18610.0.1.sock
    ([\#10072](https://www.rudder-project.org/redmine/issues/10072))
  - Fixed: Wrong permission for /etc/sudoers.d/rudder-relay file on Sles
    ([\#10065](https://www.rudder-project.org/redmine/issues/10065))
  - Fixed: Remove rudder-apache-common.conf in postinstall
    ([\#10041](https://www.rudder-project.org/redmine/issues/10041))
  - Fixed: Not having set %{real_name} does operate on /bin
    ([\#10003](https://www.rudder-project.org/redmine/issues/10003))
  - Fixed: build-caching doesn't work
    ([\#9921](https://www.rudder-project.org/redmine/issues/9921))
  - Fixed: virtualenv doesn't work in the build environment
    ([\#9824](https://www.rudder-project.org/redmine/issues/9824))
  - Fixed: version is not properly set in web interface
    ([\#10107](https://www.rudder-project.org/redmine/issues/10107))

#### Initial promises & sys tech

  - Fixed: Transient update error on ncf/local
    ([\#10028](https://www.rudder-project.org/redmine/issues/10028))
  - Fixed: Download Shared from node and  to nodes fail because /var/rudder/share-files is non existent (on centos)
    ([\#10085](https://www.rudder-project.org/redmine/issues/10085))
  - Fixed: Inventory is not resent in case of error - and agent don't report the error
    ([\#10088](https://www.rudder-project.org/redmine/issues/10088))
  - Fixed: A 4.1 agent cannot fetch its promises from a 3.1 server
    ([\#10049](https://www.rudder-project.org/redmine/issues/10049))
  - Fixed: Ignore changes generated by creation/deletion of ncf expected reports file
    ([\#10355](https://www.rudder-project.org/redmine/issues/10355))
  - Fixed: Error in relay promises when there are no shared files
    ([\#9881](https://www.rudder-project.org/redmine/issues/9881))
  - Fixed: Propagate promises error when no nodes behind a relay
    ([\#7671](https://www.rudder-project.org/redmine/issues/7671))
  - Fixed: FusionInventory --scan-homedirs should not be on by default
    ([\#7421](https://www.rudder-project.org/redmine/issues/7421))

#### System integration

  - Fixed: Error in migration (ldap backup not found because ending by .gz)
    ([\#10521](https://www.rudder-project.org/redmine/issues/10521))
  - Fixed: Apache not started on a fresh centos7 install (selinux problem)
    ([\#10426](https://www.rudder-project.org/redmine/issues/10426))
  - Fixed: On freshly installed centos7, ldap connections fail with "bad auth"
    ([\#10427](https://www.rudder-project.org/redmine/issues/10427))
  - Fixed: rudder-upgrade fails if run twice 
    ([\#10466](https://www.rudder-project.org/redmine/issues/10466))
  - Fixed: rudder-slapd force-stop doesn't exist on sles 12
    ([\#10464](https://www.rudder-project.org/redmine/issues/10464))
  - Fixed: rudder-reports doesn't start postgresql on postinstall on sles 12
    ([\#10460](https://www.rudder-project.org/redmine/issues/10460))
  - Fixed: Unable to setup metadata virtual space list
    ([\#10444](https://www.rudder-project.org/redmine/issues/10444))
  - Fixed: /var/log/rudder/ldap/slapd.log is full of not indexed message
    ([\#10429](https://www.rudder-project.org/redmine/issues/10429))
  - Fixed: Hook failed with fork: retry: No child processes
    ([\#10457](https://www.rudder-project.org/redmine/issues/10457))
  - Fixed: Log for failed login attempt is not (correctly) reported
    ([\#10259](https://www.rudder-project.org/redmine/issues/10259))
  - Fixed: After running rudder-init, no connectivity to postgresql
    ([\#10486](https://www.rudder-project.org/redmine/issues/10486))
  - Fixed: Clean-up and add build information in META-INF
    ([\#10253](https://www.rudder-project.org/redmine/issues/10253))

#### Relay server or API

  - Fixed: Error in the cron job prevents purging expired files shared between nodes
    ([\#10417](https://www.rudder-project.org/redmine/issues/10417))
  - Fixed: Allow dots in file_id in shared-files api
    ([\#10338](https://www.rudder-project.org/redmine/issues/10338))
  - Fixed: Remote-run exec for root fail with "rudder agent was interrupted"
    ([\#10185](https://www.rudder-project.org/redmine/issues/10185))

#### Web - Compliance & node report

  - Fixed: Several core features don't work anymore with more than 1000 nodes
    ([\#10456](https://www.rudder-project.org/redmine/issues/10456))
  - Fixed: Recent changes aren't display sometimes on Rules list
    ([\#10194](https://www.rudder-project.org/redmine/issues/10194))

#### Architecture - Dependencies

  - Fixed: Test broken with "FileNotFoundException /ldap/bootstrap.ldif"
    ([\#10147](https://www.rudder-project.org/redmine/issues/10147))
  - Fixed: warning: Class javax.annotation.Nonnull not found - continuing with a stub.
    ([\#10146](https://www.rudder-project.org/redmine/issues/10146))
  - Fixed: Update monix (critical bug fix)
    ([\#10393](https://www.rudder-project.org/redmine/issues/10393))

#### Performance and scalability

  - Fixed: If I click on "Regenerate all policies", it clears the cache of changes, and slows down a lot the web interface
    ([\#10383](https://www.rudder-project.org/redmine/issues/10383))
  - Fixed: Enable gzip compression on text resources
    ([\#10365](https://www.rudder-project.org/redmine/issues/10365))

#### Server components

  - Fixed: slapd is not always restarted after installation of rudder-inventory-ldap
    ([\#10467](https://www.rudder-project.org/redmine/issues/10467))
  - Fixed: pass ttl through url parameters in sharedfiles api
    ([\#10138](https://www.rudder-project.org/redmine/issues/10138))
  - Fixed: the relay api shoud read nodeslist on each call
    ([\#10111](https://www.rudder-project.org/redmine/issues/10111))
  - Fixed: In debug verbosity, logs are overflowed by logs about com.zaxxer.hikari.pool
    ([\#10471](https://www.rudder-project.org/redmine/issues/10471))

#### Techniques

  - Fixed: Variable * techniques description refers to CFEngine technical vocabulary
    ([\#10363](https://www.rudder-project.org/redmine/issues/10363))
  - Fixed: "Download files from the shared folder" behaving badly?
    ([\#10312](https://www.rudder-project.org/redmine/issues/10312))
  - Fixed: Deprecate openVPN technique
    ([\#6707](https://www.rudder-project.org/redmine/issues/6707))


## Rudder 4.1.0.beta3 (2017-02-14)

### Changes

#### Web - UI & UX

  - Add an option to not display rule status/recent changes in directives screen
    ([\#10157](https://www.rudder-project.org/redmine/issues/10157))
  - Node breakdown - show actual numbers
    ([\#7422](https://www.rudder-project.org/redmine/issues/7422))

#### Documentation

  - Document the relay API
    ([\#9997](https://www.rudder-project.org/redmine/issues/9997))

#### Initial promises & sys tech

  - Use rudder agent run as cfruncommand
    ([\#10081](https://www.rudder-project.org/redmine/issues/10081))

#### Architecture - Dependencies

  - Switch to Scala 2.12 / Lift 3.0 
    ([\#10127](https://www.rudder-project.org/redmine/issues/10127))

#### Architecture - Refactoring

  - Scala actors are deprecated in scala 2.11 and removed in 2.12: update inventory-endpoint
    ([\#10119](https://www.rudder-project.org/redmine/issues/10119))

#### Techniques

  - Deprecate old techniques versions
    ([\#10159](https://www.rudder-project.org/redmine/issues/10159))

### Bug fixes

#### Web - UI & UX

  - Fixed: Status dropdown's display is broken
    ([\#10177](https://www.rudder-project.org/redmine/issues/10177))
  - Fixed: Display of new "Display compliance and recent changes columns on rule summary" setting is broken
    ([\#10173](https://www.rudder-project.org/redmine/issues/10173))
  - Fixed: Included "time ended" in Status dropdown
    ([\#10133](https://www.rudder-project.org/redmine/issues/10133))
  - Fixed: On Group creation, the tooltip on the "Save" button doesn't appear when it is disabled
    ([\#10116](https://www.rudder-project.org/redmine/issues/10116))
  - Fixed: Broken text fields in directive form
    ([\#10164](https://www.rudder-project.org/redmine/issues/10164))

#### Web - Config management

  - Fixed: Deadlock with simultaneous generation and new reports
    ([\#10168](https://www.rudder-project.org/redmine/issues/10168))
  - Fixed: Incomplete logging in expected reports computation
    ([\#10143](https://www.rudder-project.org/redmine/issues/10143))
  - Fixed: Renable WriteSystemTechniquesTest
    ([\#10150](https://www.rudder-project.org/redmine/issues/10150))

#### Documentation

  - Fixed: Broken link in CFEngine doc
    ([\#10151](https://www.rudder-project.org/redmine/issues/10151))

#### Packaging

  - Fixed: the shared-files directory is owned by root
    ([\#10178](https://www.rudder-project.org/redmine/issues/10178))
  - Fixed: openjdk8 cannot be installed if there is a backport in the building os
    ([\#10163](https://www.rudder-project.org/redmine/issues/10163))
  - Fixed: rudder-techniques depends on perl(XML::TreePP)
    ([\#9845](https://www.rudder-project.org/redmine/issues/9845))
  - Fixed: Missing entry in rudder-web.properties after update to 4.1.0.b2
    ([\#10132](https://www.rudder-project.org/redmine/issues/10132))
  - Fixed: rudder-relay has bad "sed" line
    ([\#10131](https://www.rudder-project.org/redmine/issues/10131))

#### Initial promises & sys tech

  - Fixed: Download Shared from node and  to nodes fail because /var/rudder/share-files is non existent (on centos)
    ([\#10085](https://www.rudder-project.org/redmine/issues/10085))

#### API

  - Fixed: Allow relay-api to make asynchronous remote run call with output 
    ([\#10114](https://www.rudder-project.org/redmine/issues/10114))

#### Architecture - Dependencies

  - Fixed: Test broken with "FileNotFoundException /ldap/bootstrap.ldif"
    ([\#10147](https://www.rudder-project.org/redmine/issues/10147))
  - Fixed: warning: Class javax.annotation.Nonnull not found - continuing with a stub.
    ([\#10146](https://www.rudder-project.org/redmine/issues/10146))
  - Fixed: warning: Class javax.annotation.Nonnull not found - continuing with a stub.
    ([\#10146](https://www.rudder-project.org/redmine/issues/10146))
  - Fixed: Use correct repository definition in pom.xml
    ([\#10120](https://www.rudder-project.org/redmine/issues/10120))

#### Server components

  - Fixed: pass ttl through url parameters in sharedfiles api
    ([\#10138](https://www.rudder-project.org/redmine/issues/10138))

### Release notes

Special thanks go out to the following individuals who invested time,
patience, testing, patches or bug reports to make this version of Rudder
better:

  - Janos Mattyasovszky

This software is in beta status and contains several new features but we
have tested it and believe it to be free of any critical bugs.¬The use
on production systems is not encouraged at this time and is at your own
risk. However, we do encourage testing, and welcome all and any
feedback\!



## Rudder 4.1.0~beta2 (2017-02-02)

### Changes

#### Web - UI & UX

  - Reorganize Rules page interface ([\#9960](http://www.rudder-project.org/redmine/issues/9960))

#### Web - Config management

  - Remove all datasource code from Rudder main and add needed hooks ([\#10050](http://www.rudder-project.org/redmine/issues/10050))

#### Agent

  - Extend rudder-sign to add new information ([\#9996](http://www.rudder-project.org/redmine/issues/9996))
  - Warn the user if rudder agent is not run as root ([\#9684](http://www.rudder-project.org/redmine/issues/9684))

#### Packaging

  - Permit skipping scala build within packages ([\#10055](http://www.rudder-project.org/redmine/issues/10055))
  - use suse_version instead of sles_version during build ([\#9919](http://www.rudder-project.org/redmine/issues/9919))
  - Automatically set year in Rudder interface at build time ([\#9891](http://www.rudder-project.org/redmine/issues/9891))

#### API

  - Deprecate API v5, v6 and v7, and remove API v2,3,4 ([\#9836](http://www.rudder-project.org/redmine/issues/9836))
  - Remote run API should use relay API ([\#9714](http://www.rudder-project.org/redmine/issues/9714))

#### Architecture - Dependencies

  -  Requires Java8 (jdk8) for Rudder 4.1 ([\#9917](http://www.rudder-project.org/redmine/issues/9917))

### Bug fixes

#### Packaging

  - Fixed: Wrong ncf version dependency in 4.1 ([\#10091](http://www.rudder-project.org/redmine/issues/10091))
  - Fixed: On CentOS relay API uses /etc/httpd/logs/wsgi.18610.0.1.sock ([\#10072](http://www.rudder-project.org/redmine/issues/10072))
  - Fixed: The user trying to open nodes list in relay-api is not rudder ([\#10068](http://www.rudder-project.org/redmine/issues/10068))
  - Fixed: Wrong permission for /etc/sudoers.d/rudder-relay file on Sles ([\#10065](http://www.rudder-project.org/redmine/issues/10065))
  - Fixed: Remove rudder-apache-common.conf in postinstall ([\#10041](http://www.rudder-project.org/redmine/issues/10041))
  - Fixed: Not having set %{real_name} does operate on /bin ([\#10003](http://www.rudder-project.org/redmine/issues/10003))
  - Fixed: Allow to restrict edits on sudoers during install ([\#10001](http://www.rudder-project.org/redmine/issues/10001))

#### Web - Config management

  - Fixed: When I save a Directive, after cliking "save", it's not possible to scroll anymore in the Directive tree ([\#10010](http://www.rudder-project.org/redmine/issues/10010))

#### Server components

  - Fixed: the relay api shoud read nodeslist on each call ([\#10111](http://www.rudder-project.org/redmine/issues/10111))

### Release notes

Special thanks go out to the following individuals who invested time,
patience, testing, patches or bug reports to make this version of Rudder
better:

  - Janos Mattyasovszky

This software is in beta status and contains several new features but we
have tested it and believe it to be free of any critical bugs.¬The use
on production systems is not encouraged at this time and is at your own
risk. However, we do encourage testing, and welcome all and any
feedback\!


## Rudder 4.1.0~beta1 (2017-01-17)

### Changes

#### Web - Config management

  - Add tags in Directive/Rules ([\#9733](http://www.rudder-project.org/redmine/issues/9733))
  - Import node properties from external data sources ([\#9698](http://www.rudder-project.org/redmine/issues/9698))

#### API

  - Add a Relay API:  share files between nodes, launch run on remote run behind relay ([\#9707](http://www.rudder-project.org/redmine/issues/9707))

#### Server components

  - Implement notifications for different server-side actions and events (hooks) ([\#8353](http://www.rudder-project.org/redmine/issues/8353))

#### Web - UI & UX

  - Improve Json display in the Nodes properties tab ([\#9984](http://www.rudder-project.org/redmine/issues/9984))

#### Packaging

  - ncf-api-venv user should not have access to a shell ([\#9993](http://www.rudder-project.org/redmine/issues/9993))
  - Build slapd with lmdb ([\#9839](http://www.rudder-project.org/redmine/issues/9839))
  - Upgrade CFEngine in Rudder agent to 3.10 ([\#9737](http://www.rudder-project.org/redmine/issues/9737))

#### System integration

  - Do not create a temporary cron a postinstall ([\#9860](http://www.rudder-project.org/redmine/issues/9860))

#### Architecture - Refactoring

  - Store node compliance in database ([\#9645](http://www.rudder-project.org/redmine/issues/9645))

#### Architecture - Internal libs

  - Change pom version on master to 4.1 ([\#9686](http://www.rudder-project.org/redmine/issues/9686))

#### Documentation

  - Prepare manual for 4.1 ([\#9887](http://www.rudder-project.org/redmine/issues/9887))
  - Change doc title for 4.1 ([\#9753](http://www.rudder-project.org/redmine/issues/9753))

### Bug fixes

#### Web - UI & UX

  - Fixed: Put in bold rule form's required fields label ([\#9949](http://www.rudder-project.org/redmine/issues/9949))
  - Fixed: Nothing happens when trying to save a Directive ([\#9948](http://www.rudder-project.org/redmine/issues/9948))
  - Fixed: Put in bold "Technique version" label ([\#9935](http://www.rudder-project.org/redmine/issues/9935))

#### Packaging

  - Fixed: build-caching doesn't work ([\#9921](http://www.rudder-project.org/redmine/issues/9921))
  - Fixed: virtualenv doesn't work in the build environment ([\#9824](http://www.rudder-project.org/redmine/issues/9824))

#### Initial promises & sys tech

  - Fixed: FusionInventory --scan-homedirs should not be on by default ([\#7421](http://www.rudder-project.org/redmine/issues/7421))

#### Documentation

  - Fixed: We should disable link tests for the manual on master  ([\#9803](http://www.rudder-project.org/redmine/issues/9803))

#### Web - Config management

  - Fixed: Rule details text can be misleading ([\#6143](http://www.rudder-project.org/redmine/issues/6143))

### Release notes

Special thanks go out to the following individuals who invested time,
patience, testing, patches or bug reports to make this version of Rudder
better:

  - Florial Heigl 
  - Janos Mattyasovszky

This software is in beta status and contains several new features but we
have tested it and believe it to be free of any critical bugs.¬The use
on production systems is not encouraged at this time and is at your own
risk. However, we do encourage testing, and welcome all and any
feedback\!
