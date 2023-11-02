```php{all|7|7,3|8|8,4|8,4,17-20}
namespace App\BoardGameBlog\Infrastructure\Sylius\Resource;

use Sylius\Resource\Metadata\AsResource;
use Sylius\Resource\Model\ResourceInterface;
use Symfony\\Validator\Constraints\NotBlank;

#[AsResource(driver: false)]
final class BoardGameResource implements ResourceInterface
{
    public function __construct(
        public ?string $id = null,
        #[NotBlank] public ?string $name = null,
        public ?string $shortDescription = null,
    ) {
    }

    public function getId(): string
    {
        return $this->id;
    }
}

```
