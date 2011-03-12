What
===

This is a simple tool to help you out when creating repos in Beanstalk that follow a set template.

This isn't (yet) a general command line tool that will give you to access all of the features of Beanstalk.

How
===

To create a repo try this:

`$ beanstalk create test_repo green`

Installation
=======

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

Type `beanstalk help` for help.

Methods
=====

`$beanstalk create` - will guide you through creating a repo with optional Staging and Production environments

`$beanstalk list` - return a list of repos

`$beanstalk changes <repo_name>` - will list the most recent changes, grouped by date then ordered by time, with the revision and author

`$beanstalk releases <repo_name>` - will list the most recent releases, grouped by date then ordered by time, with the revision and author

`$beanstalk repo <repo_name>` - will show info, and server environments for a repo

`$beanstalk deploy <repo_name>` - will allow you to deploy an environment. The script will prompt you for all details.

`$beanstalk deploy-all <repo_name>` - will allow you to re-deploy all files to an environment. The script will prompt you for all details.

`$beanstalk config` - will allow you to update your Beanstalk config details (passwords are stored as plain text!)

Notes
=====

When passing in a repo name, this must be the name and not the title. Type `$beanstalk list` to see a list of repos (the names are within brackets).

If you plan on using the `$beanstalk create <repo_name> <colour>` method to create a templated repo, and automatically create a Staging and Production server then you will need to open up the file and add in your server details. In the future these settings will be saved to a config file.

Coming Soon
===========

Re-enabling the creation of Release Servers. This will be via a wizard similar to creating repos but will allow you to use default values (stored in a config file).

Thanks
=====

Thanks to https://github.com/AzizLight/fire for inspiration (and code) to create the script!