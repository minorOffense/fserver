Feature Server
==============

Feature server for Drupal 7 is built using several "Features" from contributed modules including Services, Panels/Page Manager, Views and others. It is built this way to showcase the power of Features and what is possible by simply exporting configuration from a Drupal site.

We believe Feature Server is an import part of the Drupal ecosystem as it allows configured components to be shared.

Installation
------------

Enable the module as you would any other module.

Overview
--------

All the modules within Feature Server are themselves Features. This is done as both a demonstration of what's possible with Features as well as to leverage all the amazing APIs already available in the Drupal community.

### Feature Server
Feature Server at the core provides entity types and bundles for managing Drupal compatible projects. You can creating Project entities with bundles for a module, theme or distribution. You can then attach a Release entity to any project. Required data such as core compatibility, release notes, project machine names, etc. are all entity properties which make them light/fast to load.

This also means however you can extend the entities using the Field UI to add additional data as needed (i.e. location, taxonomy)

Some key components/dependencies in Feature Server include:

- [Ctools](http://drupal.org/project/ctools)
- [Entity Reference](http://drupal.org/project/entityreference)
- [Filehash](http://drupal.org/project/filehash)
- [Features](http://drupal.org/project/features)

Beyond the Project and Release entity types, there are two Node bundles included as well. They are used to create user-facing project and release pages. These nodes reference Fserver Projects and Releases respectively. You'll find them in the Content Types section in your Drupal administrative interface.

You can create new projects / release directly from these nodes thanks to

- [Inline Entity Form](http://drupal.org/project/inline_entity_form)

If you want to access a project or release directly, you can manually reach 'admin/content/projects/:id' in the URL. There is no UI for browsing project and release entities directly by default. Use the project and release nodes or create your own UI (using Views for example).

### Feature Server Services
Feature Server Services uses the [Services API](http://drupal.org/project/services) to expose project and release data. An extension is included to create a Drupal Update module compatible project feed so you can expose your Features to Drupal sites. But this also allows you to use any Services compatible access control, data methods or servers for exposing this data.

### Feature Server UI
This is a basic UI for displaying lists of projects, releases and similar functionality that you would find on Drupal.org. It is not designed to be a complete solution for exposing all options available within Feature Server. Simply a guide to what is possible to build. It uses Page Manager and Panels to define the project page layouts and release page layouts. There are also some default views for showing common lists (e.g. recent releases)

This module is meant as an example to how you could build a UI for Fserver. It can be disabled/replaced by your own implementation (e.g. use Context and DS instead of Panels)

- [Panels](http://drupal.org/project/panels)

Additional Notes
----------------

This module defines 4 entity types

- project
- release
- project_type
- release_type

Thus is also implements functions in the form ````project_load```` and ````release_load````. Note that this may conflict with other modules named "project" or "release" etc.

