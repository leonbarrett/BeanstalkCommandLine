What
===

This is a simple tool to help you out when creating and deploying your Beanstalk repos.

This isn't (yet) a general command line tool that will give you to access all of the features of Beanstalk.

How
===

To create a repo try this:

`$ beanstalk -m repo:create -r test_repo --colour green`

Installation
=======

Ensure you have PHP installed as CLI. Run `php -v` to check

Download the file and make it executable

`chmod a+x beanstalk`

Either place it in your path, or add to your path.

`echo 'export PATH=YOURPATHHERE:$PATH' >> ~/.profile`

When using the tool for the 1st time you will be prompted to add in your Beanstalk details.

You can also add a beanstalk_cli.config to your home directory containing:

`[account_settings]
account = ACCOUNT_NAME
username = USER_NAME
password = PASSWORD`

If you want to store your Beanstalk password in your Keychain rather than in plain text you can read the guide on the Wiki - https://github.com/leonbarrett/BeanstalkCommandLine/wiki/Using-Keychain

Type `beanstalk --help` for help.

Methods
=====

`$beanstalk -m repo:create -r REPO_NAME -t (git/svn/mercurial) --colour blue` - will guide you through creating a repo with optional Staging and Production environments

`$beanstalk -m repo:list` - return a list of repos

`$beanstalk -m repo:search -r REPO_NAME` - search for a repo

`$beanstalk -m repo:changes -r REPO_NAME` - will list the most recent changes, grouped by date then ordered by time, with the revision and author

`$beanstalk -m repo:releases -r REPO_NAME` - will list the most recent releases, grouped by date then ordered by time, with the revision and author

`$beanstalk -m repo:info -r REPO_NAME` - will show info, and server environments for a repo

`$beanstalk -m repo:deploy -r REPO_NAME -e ENVIRONMENT_NAME -c "commit message" -v REVISION` - will allow you to deploy an environment. The script will prompt you for all details if not passed in.

`$beanstalk -m repo:deployall -r REPO_NAME -e ENVIRONMENT_NAME -c "commit message" -v REVISION` - will allow you to re-deploy all files to an environment. The script will prompt you for all details if not passed in.


`$beanstalk account:config` - will allow you to update your Beanstalk config details (passwords are stored as plain text!)

`$beanstalk keys:view` - will allow you to view your SSH keys that have been added to Beanstalk

`$beanstalk keys:create` - will allow you to add the Key on your machine to your Beanstalk account

Parameters
==========

These are global parameters that will work across the methods:

* -m or --method 		= the method name. This is required to actually do anything. See above for a list of available methods
* -r or --repository 	= repository name
* -v or --version 		= revsion (for use with deploying)
* -e or --environment	= environment name (for use with deploying)
* -c or --comment		= commit message (for use with deploying)
* -p or --path			= file path (for use with web previews)
* -t or --type			= repository type (git/svn/mercurial)
* --colour				= repository label colour

Notes
=====

When passing in a repo name, this must be the name and not the title. Type `$beanstalk -m repo:list` to see a list of repos (the names are within brackets).

Thanks
=====

Thanks to https://github.com/AzizLight/fire for inspiration (and initial code) to create the script and https://github.com/pete-otaqui/ClipClop for the library to parse the command line options
