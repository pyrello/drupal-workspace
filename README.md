# Drupal Workspace
A template project for working on Drupal 9+ projects. The project uses Drupal VM, which provides a vagrant environment for local development and testing.

## Getting started
* Clone the repo or download a copy:
  ```bash
  git clone git@github.com:pyrello/drupal-workspace.git myproject
  ```
* `cd ./myproject`
* Remove the existing git repo information:
  ```bash
  rm -rf ./.git
  ```
* Initialize a new git repo:
  ```bash
  git init
  ```
* Add initial commit, set git remote url, push to repo. See https://docs.github.com/en/free-pro-team@latest/github/importing-your-projects-to-github/adding-an-existing-project-to-github-using-the-command-line

## Local development
* Start the virtual machine:
  ```bash
  vagrant up
  ```
  This process will take a little while the first time because it is provisioning the virtual machine.
* Log into the virtual machine:
  ```bash
  vagrant ssh
  ```
* If you are just getting started, you'll need to install composer dependencies:
  ```bash
  composer install
  ```
* By default the website will be available locally at `https://local.pyrello.com`. You can change this to something else, see the section below about customizing the Drupal VM configuration.

## Customizing Drupal VM
The Drupal VM configuration file is located at `vm/config.yml`. To change the local URL for your website, change the `vagrant_hostname` value to something of your choosing. Be aware if you choose a domain that is available on the web, that this local entry will supersede that.

For full details on Drupal VM customizations, see http://docs.drupalvm.com/en/latest/getting-started/configure-drupalvm/.

Please note that changing the value of `drupal_core_path` will break your local website, unless you also rename the `web` folder to correspond to the entry in `vm/config.yml`.
