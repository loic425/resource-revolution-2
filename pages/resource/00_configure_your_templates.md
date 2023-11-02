## Configure your main templates dir

```yaml
# config/package/sylius_resource.yaml

sylius_resource:
    settings:
        default_templates_dir: '@SyliusAdminUi/crud'
```

<!--
A new feature that I want to introduce is the default templates directory configuration.

In Sylius admin panel, there are some common templates for CRUD pages.
* these default templates read the metadata from your operations to build the page title.
* the create and update templates are using a form and submit buttons
* the index template contains a grid

That will simplify a lot the operations' configuration.
Cause you will be able to skip that definition in each resource metadata.

-->
