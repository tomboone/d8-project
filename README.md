# (Customized) Composer template for Drupal projects

This is a customized version of [Drupal Composer](http://drupal-composer.org/) that removes that project's env settings and adds some requirements I use in every Drupal 8 project:

* [Bootstrap](https://www.drupal.org/project/bootstrap) theme
* A custom Bootstrap Sass [subtheme](https://github.com/tomboone/bootstrap_sass)
* [Adminimal theme](https://www.drupal.org/project/adminimal_theme)
* [Adminimal admin toolbar](https://www.drupal.org/project/adminimal_admin_toolbar)
* Some [custom scripts](https://github.com/tomboone/d8-scripts) I use for automating core/contrib updates
* A default [Lando](https://lando.dev/) config file

## Installation

To create a Drupal 8 instance from this project, just run:

`composer create-project tomboone/d8-project:~1.0 drupal --stability dev --no-interaction`


## Using with Lando 
To use the included Lando config, open `lando.yml` and in line 1 replace {LANDOPROJECT} with the name you'd like to give your project. Then run:

`lando start`

Once the Lando container is up and running, to install a Drupal site, run:

`lando drush site-install --db-url=mysql://drupal8:drupal8@database/drupal8`

To use the included Bootstrap Sass subtheme, you'll need to initialize it with Compass. The Lando config installs Compass in your container automatically, so to get started, just run the following commands:

```shell script
cd web/themes/contrib/bootstrap_sass
lando compass init
```

For additional information about the subtheme, see: https://github.com/tomboone/bootstrap_subtheme