## Use the Resource attribute

PHP attribute ```#[Resource]``` configures your entity as a Sylius resource.

```php {all|9|9,5}
namespace App\Entity;

use App\Repository\BookRepository;
use Doctrine\ORM\Mapping as ORM;
use Sylius\Component\Resource\Metadata\Resource;
use Sylius\Component\Resource\Model\ResourceInterface;

#[ORM\Entity(repositoryClass: BookRepository::class)]
#[Resource]
class Book implements ResourceInterface
{
}

```

---

### Debug command    

```bash
bin/console sylius:debug:resource 'app.book'
```

### Output

```bash
New Resource Metadata
---------------------

------------------------ ----------------------- 
  Option                   Value                  
 ------------------------ ----------------------- 
  alias                    "app.book"             
  section                  "admin"                
  formType                 "App\Form\BookType"    
  templatesDir             "@SyliusAdminUi/crud"  
  routePrefix              "/admin"               
  name                     "book"                 
  pluralName               null                   
  applicationName          "app"                  
  identifier               null                   
  normalizationContext     null                   
  denormalizationContext   null                   
  validationContext        null                   
  class                    "App\Entity\Book"      
 ------------------------ -----------------------
```