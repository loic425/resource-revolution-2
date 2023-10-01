## Adding/Editing books

<v-clicks>

We'll use `Create` and `Update` operations which allows to add a new item of your resource.

```php {all|11|11,3|14-15|14-15,4,6}
namespace App\Entity;

use App\Form\BookType;
use Sylius\Component\Resource\Metadata\Create;
use Sylius\Component\Resource\Metadata\Index;
use Sylius\Component\Resource\Metadata\Update;
use Sylius\Component\Resource\Metadata\Resource;
use Sylius\Component\Resource\Model\ResourceInterface;

#[Resource(
    formType: BookType::class,
    operations: [
        new Index(grid: BookGrid::class),
        new Create(),
        new Update(),
    ],
)]
class Book implements ResourceInterface
{
}

```

</v-clicks>

---

## Route

<v-clicks>

It will configure this route for your `create` and your `update` operations.

| Name            | Method                | Path             |
|-----------------|-----------------------|------------------|
| app_book_create | GET, POST             | /books/new       |
| app_book_update | GET, PUT, PATCH, POST | /books/{id}/edit |


</v-clicks>

---

```php {all|15-19|16|17|20-24|21|22}
final class BookGrid extends AbstractGrid implements ResourceAwareGridInterface
{
    // [...]

    public function buildGrid(GridBuilderInterface $gridBuilder): void
    {
        $gridBuilder
            ->orderBy('name', 'asc')
            ->addField(
                // [...]
            )
            ->addField(
                // [...]
            )
            ->addActionGroup(
                MainActionGroup::create(
                    CreateAction::create(),
                )
            )
            ->addActionGroup(
                ItemActionGroup::create(
                    UpdateAction::create(),
                )
            )
        ;
    }

    public function getResourceClass(): string
    {
        return Book::class;
    }
}

```

---
layout: image
image: /editing_book_01.png
transition: fade
---

---
layout: image
image: /adding_book_02.png
transition: fade
---

---
layout: image
image: /adding_book_03.png
transition: fade
---

---
layout: image
image: /adding_book_04.png
transition: fade
---

---
layout: image
image: /adding_book_05.png
transition: fade
---

---
layout: image
image: /editing_book_03.png
transition: fade
---

---
layout: image
image: /editing_book_04.png
transition: fade
---