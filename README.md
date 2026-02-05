PHP Manager 2 for IIS
=====================



[![Build](https://img.shields.io/github/actions/workflow/status/phpmanager/phpmanager/dotnet-desktop.yml?branch=master&label=Build%20status&style=flat-square)](https://github.com/phpmanager/phpmanager/actions/workflows/dotnet-desktop.yml)
[![Github All Releases](https://img.shields.io/github/downloads/phpmanager/phpmanager/total.svg?label=Total%20downloads&style=flat-square)](https://github.com/phpmanager/phpmanager/releases)

New Attempt to fully take over the old project on [CodePlex](http://phpmanager.codeplex.com),

* Fully automated build process on AppVeyor.
* Trustable MSI installers with IIS 10 support.
* Bug fixes and new features if needed.
* Organize a group of new maintainers to work on this project.

If you want to join, please respond to https://github.com/phpmanager/phpmanager/issues/1 .

The new home page for this project is http://www.phpmanager.xyz .

Update
------
[Microsoft ended its efforts to bring PHP to Windows/IIS](https://news-web.php.net/php.internals/110907), so this project is in maintenance mode. We are modernizing for PHP 8.x—see the plan below and contribute if you can.

PHP 8.x modernization plan
--------------------------
* Validate PHP 8.x handlers end-to-end (FastCGI mapping, php.ini defaults, extension toggles such as `php_gd.dll` vs `php_gd2.dll`) and expand lifecycle metadata for 8.3/8.4 in `Server/Config/PHPConfigHelper.cs`.
* Update installers to bundle the correct Visual C++ runtime for PHP 8.x builds and refresh Wix/MSI metadata so new binaries register cleanly with IIS.
* Refresh PowerShell/chocolatey packaging to pick up current PHP 8.x builds and ensure the manager detects them without manual configuration.
* Add a winget flow alongside chocolatey so Windows users can install PHP 8.x quickly: `choco install php --version=8.3.6` or `winget install --id PHP.PHP --version 8.3.6`, then register the installed path in PHP Manager.
* Extend automated validation (unit/UI smoke where available) to cover PHP 8.x registration and recommended settings on IIS 10+.
