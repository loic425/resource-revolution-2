## Removing books

<v-clicks>

We'll use `Delete` and `Bulk delete` operations which allows to remove existing items of your resource.

```php {all|15-16|15-16,4,6}
namespace App\Entity;

use App\Form\BookType;
use Sylius\Resource\Metadata\BulkDelete;
use Sylius\Resource\Metadata\Create;
use Sylius\Resource\Metadata\Delete;
// [...]

#[AsResource(
    formType: BookType::class,
    operations: [
        new Index(grid: BookGrid::class),
        new Create(),
        new Update(),
        new Delete(),
        new BulkDelete(),
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

It will configure this route for your `delete` and `bulk_delete` operations.

| Name                 | Method       | Path               |
|----------------------|--------------|--------------------|
| app_book_delete      | DELETE, POST | /books/{id}/delete |
| app_book_bulk_delete | DELETE, POST | /books/bulk_delete |

</v-clicks>

---

```php {all|12-17|14|15|18-22|19|20}
final class BookGrid extends AbstractGrid implements ResourceAwareGridInterface
{
    // [...]

    public function buildGrid(GridBuilderInterface $gridBuilder): void
    {
        $gridBuilder
            // [...]
            ->addActionGroup(
                // [...]
            )
            ->addActionGroup(
                ItemActionGroup::create(
                    UpdateAction::create(),
                    DeleteAction::create(),
                )
            )
            ->addActionGroup(
                BulkActionGroup::create(
                    DeleteAction::create()
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
image: /removing_many_books_01.png
transition: fade
---

---
layout: image
image: /removing_book_02.png
transition: fade
---

---
layout: image
image: /removing_book_03.png
transition: fade
---

---
layout: image
image: /removing_many_books_02.png
transition: fade
---

---
layout: image
image: /removing_many_books_03.png
transition: fade
---

---
layout: image
image: /removing_many_books_04.png
transition: fade
---
