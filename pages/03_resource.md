---
class: 'text-center'
---

<div align="center">
<img class="w-75" align="center" src="https://sylius.com/wp-content/uploads/2021/03/sylius-logo_sylius-logo-light-1024x422.jpg">
</div>

## Resource Bundle

<!--
Now let's continue with the main topic of my talk: the Resource bundle.
-->

---

###  Past use cases

<v-clicks>

* Making CRUD with Doctrine entities.
* Avoiding writing controllers that all do the same things.

</v-clicks>

<!--
It was originally created: 
* to make CRUD with Doctrine entities,
* and to avoid writing controllers that all do the same things.
-->

---

### Today use cases

<v-clicks>

* Better DX
* Customize persistence layer : ERP, Elastic search...
* Allow to use in DDD projects

</v-clicks>

<!--
Now we want:
* a better DX
* we also want to customize the persistence layer such as an ERP or Elastic search for example.
* and we want to use it in DDD projects.
-->

---

# New Sylius Resource System

<v-clicks>

* API Platform for the inspiration
* Akawaka & Commerce Weavers for sponsoring that development
* Łukasz Chruściel at Commerce Weavers for the code reviews

</v-clicks>

<!--
To fulfil these requirements, 
I've created a new Sylius resource system.

* Basically, it's based on API Platform internals, so we can thank this project and their core team members for the inspiration.
* To make that happen, I've submitted about one hundred and twenty pull requests.
So it was a lot of work for me, but also for reviews. So we can thank Akawaka & Commerce Weavers for sponsoring that development.
* And Łukasz Chruściel for all the reviews.
-->

---
src: ./resource/00_configure_your_templates.md
---

---
src: ./resource/01_configure_your_resource.md
---

---
src: ./resource/02_index_operation.md
---

---
src: ./resource/03_create_operation.md
---

---
src: ./resource/05_delete_operation.md
---

---
src: ./resource/07_apply_transition_operation.md
---

---
src: ./resource/08_processor.md
---

---
src: ./resource/09_bulk_update_operation.md
---
