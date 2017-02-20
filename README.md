# Giraffe
(Javascript and PHP) Ajax: Server/Client Helper/Router

## Install: Server Side Usage

**index.php / bootstrap.php**


_Add this to one or both of these php files_


```
use Giraffe\Giraffe;
Giraffe::setEnvironment(ENVIRONMENT);
Giraffe::setProject('MY SITE NAME OR PRJECT NAME');
Giraffe::setDeveloperEmails(
     'me@mailprovider.co.uk,my_partner@theirmailprovider.co.uk'
);
```
**Put a route in place to get to an ajax controller**

_Here is an example of how that ajax controller may look_

```
namespace MyApp\Ajax;

use Giraffe\Giraffe;

class Ajax 
{
    public function someMethodYouRouteToForAjax()
    {
        $allowedControllers = [Login::class, Dashboard::class];
        new Giraffe($allowedControllers, 'MyApp\\Controller\\', 'ajax', MYAPP_PATH . '/Views/ajax/');
    }
}



