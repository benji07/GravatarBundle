Installation
============

  1. Add this bundle to your project as Git submodules:

          $ git submodule add git://github.com/dator/GravatarBundle.git src/Bundle/GravatarBundle


  2. Add this bundle to your application's kernel:

          // application/ApplicationKernel.php
          public function registerBundles()
          {
              return array(
                  // ...
                  new Bundle\GravatarBundle\GravatarBundle(),
                  // ...
              );
          }

  3. Configure the `gravatar` service and helper in your config:

          # application/config/config.yml
          gravatar.config: ~

  4. If you always have some default for your gravatars such as size, rating or default it can be configured in your config

         # application/config/config.yml
         gravatar.config:
            rating: g
            size: 80
            default: ~

  5. If you use Twig and this in your config:

         gravatar.twig: ~

Usage
=====

All you have to do is use the helper like this example:

      <img src="<?php echo $view['gravatar']->getUrl('alias@domain.tld') ?>" />

Or with parameters:

      <img src="<?php echo $view['gravatar']->getUrl('alias@domain.tld', '80', 'g', 'defaultimage.png') ?>" />

The only required parameter is the email adress. The rest have default values.

If you use twig you can use the helper like this exemple:

      {% gravatar "alias@domain.tld" %}
      
Or with parameters:

      {% gravatar "alias@domain.tld" with ['size': '80', 'rating' : 'g', 'default': 'defaultimage.png'] %}

For more information [look at the gravatar implementation pages][gravatar].

[gravatar]: http://en.gravatar.com/site/implement/
