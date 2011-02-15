What
===

This is a simple tool to help you out when creating repos in Beanstalk that follow a set template.

This isn't a general command line tool, to access all of the features of Beanstalk.

How
===

`$ beanstalk create test_repo green`

Installation
=======

Download the file and make it executable

`chmod a+x beanstalk`

Either place it in your path, or add to your path.

`PATH=/Users/user_name/bin:$PATH`

Methods
=====


create - will create an SVN repo and add the staging and production release servers (update the script with your details for this to work)

list - return a list of repos

create-empty - will create an SVN repo without any release servers

create-git - will create an empty GIT repo

Thanks
=====

Thanks to https://github.com/AzizLight/fire for inspiration (and code) to create the script!