## Browsing books

<v-clicks>

We'll use `Index` operation which allows to browse all items of your resource.

```php {all|8-10|8-10,3|12-14}
namespace App\Entity;

use Sylius\Resource\Metadata\Index;
use Sylius\Resource\Metadata\AsResource;
use Sylius\Resource\Model\ResourceInterface;

#[AsResource(
    operations: [
        new Index(),
    ],
)]
// OR
#[AsResource]
#[Index]
class Book implements ResourceInterface
{
}

```

</v-clicks>

---

## Route

<v-clicks>

It will configure this route for your `index` operation.

| Name                  | Method          | Path    |
|-----------------------|-----------------|---------|
| app_book_index        | GET             | /books  |

</v-clicks>

--- 

## Tips

<v-clicks>

```bash
bin/console sylius:debug:resource app_book_index
```

```bash
Operation Metadata
------------------

 ------------------------ -------------------------------------------------------------------- 
Option                   Value
 ------------------------ -------------------------------------------------------------------- 
twigContextFactory       "sylius.twig.context.factory.default"                               
methods                  [                                                                   
"GET"                                                             
]                                                                   
path                     null                                                                
routeName                "app_book_index"                                              
routePrefix              null                                                         
redirectToRoute          null                                                                
redirectArguments        null                                                                
provider                 "Sylius\Resource\Symfony\Request\State\Provider"          
processor                "Sylius\Resource\Doctrine\Common\State\PersistProcessor"  
responder                "Sylius\Resource\Symfony\Request\State\Responder"         
repository               "app.repository.book"                                               
template                 "@SyliusAdminUi/crud/index.html.twig"
#[...]
```

</v-clicks>

---

## Create a grid

You can use the Grid maker.

```bash
$ bin/console make:grid
```

---

```php {all|1|3-6|11|12-16|17-21}
final class BookGrid extends AbstractGrid implements ResourceAwareGridInterface
{
    public static function getName(): string
    {
        return 'app_book';
    }

    public function buildGrid(GridBuilderInterface $gridBuilder): void
    {
        $gridBuilder
            ->orderBy('name', 'asc')
            ->addField(
                StringField::create('name')
                    ->setLabel('sylius.ui.name')
                    ->setSortable(true)
            )
            ->addField(
                StringField::create('author')
                    ->setLabel('sylius.ui.author')
                    ->setSortable(true)
            )
        ;    
    }
```

---

## Use this grid for your index operation

<v-clicks>

To use a grid for you operation, you need to install the [Sylius grid package](https://github.com/Sylius/SyliusGridBundle/)

```php {all|9-10|9-10,3|11-12|11-12}
namespace App\Entity;

use App\Grid\BookGrid;
use Sylius\Resource\Metadata\Index;
use Sylius\Resource\Metadata\AsResource;
use Sylius\Resource\Model\ResourceInterface;

#[AsResource]
// You can use either the FQCN of your grid
#[Index(grid: BookGrid::class)]
// Or you can use the grid name
#[Index(grid: 'app_book')]
class Book implements ResourceInterface
{
}

```

</v-clicks>

---

```bash
bin/console sylius:debug:resource app_book_index
```

```bash
Operation Metadata
------------------

 ------------------------ -------------------------------------------------------------------- 
Option                   Value
 ------------------------ -------------------------------------------------------------------- 
#[...]                                                            
provider                 "Sylius\Resource\Grid\State\RequestGridProvider"        
#[...]
```

---
layout: image
image: /browsing_books_01.png
---
