---
layout: image-right
image: https://ressources.mobizel.com/wp-content/uploads/2019/12/monofony-banner-mobizel-2048x707.png
---

# What is Monofony and Why use it?

<v-clicks>

* Bootstrapping a modern application on top of Symfony
* Leveraging Sylius bundles and components
* Helping you to focus more on what truly matters to your use-case

</v-clicks>

---
hideInToc: true
---

# Installation

```shell
$ composer create-project monofony/skeleton project_name
```

<!--
To set up the project, there is a skeleton which uses Flex to copy some basic features into your project.
-->

---
layout: image
image: /dashboard.png
transition: fade
---

<!--
The installation comes with an admin pack.
It contains a minimal dashboard and some basic CRUDs to manage administrators and customers.

All these features can be customized, improved or simply removed.
-->

---
layout: image
image: /administrators.png
---

<!--
Here is a grid of administrators.

Does everybody know what is a Grid?

Basically, a grid is an object which contains the table data, the filters and some action buttons, such as the edit, delete and also the create buttons.
-->

---

## Monofony API Pack

```shell
$ composer require monofony/api-pack "^0.10"
```

<br />

* voir [l'installation détaillée dans la doc](https://docs.monofony.com/current/setup/application).

<!--
Optionally, you can install the api-pack.
-->

---
layout: image
image: /api_pack.png
---

<!--
It will copy some basic endpoints such as the login, the customer registration and endpoints to reset password.
-->
