# Pythian - DevOps Consultant Challenge

## Overview

At Pythian, our DevOps Consultants must have a wide depth of knowledge across several key technologies.  The team expects that its members will be curious and constantly learning.  We do this to improve our skills so that we can deliver value to our clients, and be thought leaders within their organizations, as well as within Pythian.

Part of our interview process for prospective candidates is this techical challenge.  It exists to give you an opportunity to show off your skillset.  It also allows us to see how you approach a new problem, and the type of solution that you create.

You can expect to spend 1-3 hours on this challenge.

## What you'll be building

For this challenge, you'll be building a Vagrantfile that installs and configures an application of your choice.  It's highly suggested that you use a configuration management tool, like Puppet; Chef; DSC; Salt; or Ansible, to perform the configuration of your VM, versus a scripting language like Bash or Powershell.  Use the best tool for the job, but consider at least performing some configuration with a configuration management tool, as we use them regularly in our work.

We've received challenges that install Wordpress, IIS, or even Apache.  Use what you know.

You'll also be writing a simple script to query http://checkip.dyndns.org, and append the output to a file.  This script can be written in the language of your choice, and should be created on your vagrant box when running `vagrant up`.  Feel free to install any dependencies your script needs via your Vagrantfile.

The script should append output to the file in the following format.

`<datetimestamp> | <script output>`

Here is a bulleted list to help with the requirements.

  * Use one of the included Vagrantfile files to construct a VM.
  * Modify the Vagrantfile to install a web app of your choice.
  * Modify the Vagrantfile to configure the web app and OS.
  * Create a script that queries `checkip.dyndns.org`, and appends the output to a file (see the format requirements above).
  * Create a text document that explains how your script

## Review Guidelines

We evaluate challenge responses using the following criteria

  * Does the solution work?
  * Is the code consistently styled?
  * Is the code easy to read and understand when reviewed by an experienced DevOps team member?
  * Is the entire solution representative of the quality of work that would be expected from a member of our DevOps team?  Examples of this include
    * Use of parameters instead of hard-coded values, where appropriate.
    * Error handling.
    * Helpful documentation.
    * Use of popular libraries (modules, recipes, plugins, etc...), where appropriate.

## Solution Submission

We prefer that final solutions be delivered via a public GitHub repository.  Please note that due to the nature of public GitHub repositories, your solution will be publicly available for as long as you keep the repository.

Other arrangements can be made for circumstances in which candidates are not comfortable releasing their code via a publicly accessible repository.  Please let us know if you would prefer an alternate method of sending your solution.  It's preferred that the version control history be maintained so that it may be reviewed.

## Technical Guidelines

In order to speed up the review process, we ask that you adhere to the following guidelines.

  * Use Vagrant 1.8.4 or greater.
  * Create a text document in your project folder that contains the following information
    * The version of Vagrant that you used for testing.
    * Any Vagrant plugins that need to be installed to run your solution.
  * Use the windows or linux box that's included in the default Vagrantfile files.
    * If you must use a different box, update the `config.vm.box_url` variable in the Vagrantfile.