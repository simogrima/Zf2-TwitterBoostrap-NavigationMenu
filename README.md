Zf2-TwitterBoostrap-NavigationMenu
==================================

Zend Framework 2 Navigation Menu Twitter Bootstrap Integration

Navigation Factory:


namespace Application\Navigation\Service;
 
use Zend\Navigation\Service\DefaultNavigationFactory;
 
 
class MyNavigationFactory extends DefaultNavigationFactory
{
 
    protected function getName()
    {
        return 'mynav';
    }
}
