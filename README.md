# ACSF Drush Alias Generator

A simple shell script to quickly create Drush aliases for your Acquia Cloud Site Factory (ACSF) Drupal sites. This tool makes it easy to run Drush commands against your ACSF sites from your local development environment.

When you run the script, it automatically generates Drush aliases for the **Test (01test), Dev (01dev), and Live (01live)** environments of the selected Drupal site.

The script is easy to modify, allowing you to add additional ACSF environments if needed, such as **Test 2 (02test), Dev 2 (02dev),** etc.

The generated `.yml` files will be stored in the `drush/sites/` folder, enabling you to run Drush commands effortlessly against your ACSF sites from your development environment.

## Setup

### 1. Create the necessary folders
Inside your Drupal project's root directory (next to `config/`, `docroot/`, `composer.json`, and `composer.lock`), run:  

```bash
mkdir -p drush/sites
```

### 2. Download the script
- Download `acsf-drush-alias.sh` from this repository and place it in your Drupal project's root directory.  
- Alternatively, create a new Bash script named `acsf-drush-alias.sh` and copy the content from this repository's script.  

### 3. Configure your ACSF application name
- Open `acsf-drush-alias.sh` in a text editor.
- Find the `acsf_app_name` variable and update it with your ACSF application name.

### 4. Make the script executable
- To run the script, you first need to make it executable. In your terminal, run:
```bash
chmod +x acsf-drush-alias.sh
```

## Usage

Run the script with:

```bash
./acsf-drush-alias.sh
```

Follow the on-screen instructions to create a Drush alias for an ACSF site.  

## Running Drush Commands

Once the alias is created, you can run Drush commands using this format:

```bash
drush @sitename.environment drush_command
```

### Example

```bash
drush @yoursite.01live status
```

This will check the status of your ACSF site in the `01live` environment.

## Terminal UI usage example

```code
Signorelli IDE:~/project (main) $ ./acsf-drush-alias.sh

             <------->
         <--------------->
<--------------------------------->
|    ACSF Drush Alias Generator    |
<--------------------------------->
         <--------------->
             <------->

      |---------------------|
      |      Main Menu      |
      |---------------------|
      | 1 - New Drush Alias |
      | 2 - Exit            |
      |---------------------|

Select a number from the Main Menu: 1

Selected: New Drush Alias
-------------------------

Make sure to enter the name of a site that already exists in your ACSF account.
Example: If your site's ACSF URL is:
site1.your_acsf_app_name.acsitefactory.com
Enter site1

Enter the name of the site for which you want to create a Drush alias: site1

Is this site name correct?: "site1" (Yes/No/Cancel = y/n/c)
y

Generating the drush alias for site1..

Ready! Going back to the Main Menu...

      |---------------------|
      |      Main Menu      |
      |---------------------|
      | 1 - New Drush Alias |
      | 2 - Exit            |
      |---------------------|

Select a number from the Main Menu: 2

Selected: Exit
--------------
Exiting this script...

Signorelli IDE:~/project (main) $
```

### Acquia Cloud Site Factory Tutorials & Guides

I have written and published two in-depth technical guides on Acquia Cloud Site Factory for the Acquia Developer Portal. In these guides, I use this shell script to quickly generate Drush aliases for new ACSF sites.

Here are the tutorials:  
- **[Preparing a Codebase for Site Factory](https://dev.acquia.com/tutorial/preparing-codebase-site-factory-part-1)**
- **[Configuring a Drupal 10 Codebase with Acquia CMS and Site Studio for Site Factory](https://dev.acquia.com/tutorial/configure-drupal-10-codebase-drupal-cms-and-site-studio-site-factory-part-1)**

These guides provide a step-by-step approach to setting up and managing ACSF codebases efficiently. If you're working with ACSF, I highly recommend checking them out! 🚀