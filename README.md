ci-project
==========

Blank master repository for CodeIgniter based web projects.

Contains only the installation dependant files and the project folder structure, all project components are
added as git submodules.

Purpose
-------

* Move all PHP code outside of the public web root, leaving only their entry points (index.php, etc)
* Have the least cluttered folder/file structure possible, one folder - seen from the top
* Ease use of submodules
* Keep application code base(s) clean of temporary/generated files
* Preview use of several applications
* Have one common place for packages
* Allow installation of additional language packs as submodules
* Have all write access required files under one folder (temp)
* Have one common assets folder under public root

Repository Branches
-------------------

**master**  
For manual setup

**v2.1.2**  
Branches with CodeIgniter version numbers (CodeIgniter repo tags prefixed with v) come with a custom index.php file which contains a server name dependant, centralized setup based on environments


Directory structure
-------------------

I prefix the application name(s) with an underscore to have them appear together on top of listings.  
The packages folder is set up to easily add language packs as packages.  
The temp folder contains everything which requires write access.  
The cache and logs folders contain a folder for each application used.  
The htdocs folder represents the web root.  

/CodeIgniter/packages  
/CodeIgniter/packages/languages  
/CodeIgniter/packages/languages/language  

/CodeIgniter/temp  

/CodeIgniter/temp/backups  

/CodeIgniter/temp/cache  
/CodeIgniter/temp/cache/_application  

/CodeIgniter/temp/logs  
/CodeIgniter/temp/logs/_application  

/htdocs

Installation
------------

After cloning this repository:

**v2.1.2** Versioned Branches

1. Add a CodeIgniter repo clone as submodule into the folder CodeIgniter,
   yes, it's a little weird to have later the path CodeIgniter/CodeIgniter, You're free to change that.
2. Add Your base application as submodule under CodeIgniter/_application or create one by using
   the default application under CodeIgniter/CodeIgniter/application.


**master** Branch

Same steps as for version branches, then:

3. Copy the CodeIgniter/CodeIgniter/index.php file to htdocs/index.php.
4. Update the paths in htdocs/index.php.
5. Update the cache path and the log path in _application/config/config.php,
   I use dirname(APPPATH) to keep it installation independant.


