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


**environnements**  
This branch comes with a custom index.php file. It contains a server name dependent, centralized setup based on environments and server names.


Tags
----
CodeIgniter version numbers (CodeIgniter repo tags prefixed with v) 


Directory structure
-------------------

I prefix the application name(s) with an underscore to have them appear together on top of listings.  
The packages folder is set up to easily add language packs as packages.  
The temp folder contains everything which requires write access.  
The cache and logs folders contain a folder for each application used.  
The htdocs folder represents the web root.  

```
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
```

Installation
------------

- Clone this repository
- Checkout desired branch / version

**Branch environnements**  

- Add a CodeIgniter repo clone as submodule into the folder CodeIgniter,
   giving You CodeIgniter/CodeIgniter, You're free to change that.
- Add Your base application as submodule under CodeIgniter/_application or create one by using
   the default application under CodeIgniter/CodeIgniter/application.


**Branch master**

Same steps as for the environnements branch, then:

- Copy the CodeIgniter/CodeIgniter/index.php file to htdocs/index.php.
- Update the paths in htdocs/index.php.
- Update the cache path and the log path in _application/config/config.php,
   I use dirname(APPPATH) to keep it installation independant.
   
- Cut the links to the original repo (git remote rm)
- Add a new origin remote (git remote add, git push -u origin)


