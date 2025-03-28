# ACSF Drush Alias Generator  

A simple Bash script to quickly create Drush aliases for your Acquia Cloud Site Factory (ACSF) Drupal sites. This makes it easy to run Drush commands for your ACSF sites from your local development environment.  

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

```bash
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