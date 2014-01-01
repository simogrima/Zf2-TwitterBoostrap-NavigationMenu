Zf2-TwitterBoostrap-NavigationMenu
==================================

Simple integration of Twitter Bosstrap Navbar in the Zend Framework 2 Navigation Menu unsing a partial view helper.

Note works only with one depht level: <code>setMaxDepth(1)</code>
<h2>Integration example</h2>
Navigation Factory:
<pre>
namespace Application\Navigation\Service;
 
use Zend\Navigation\Service\DefaultNavigationFactory;
 

class MyNavigationFactory extends DefaultNavigationFactory
{
 
    protected function getName()
    {
        return 'mynav';
    }
}
</pre>
Service Manager (in a config file):
<pre>
return array(
    'service_manager' => array(
        'factories' => array(
            'my_navigation' => 'Application\Navigation\Service\MyNavigationFactory',
        ),
    ),
);
 
</pre>
Layout view:
<pre>
&lt;?php echo $this->navigation('my_navigation')
    ->menu()
    ->setUlClass('nav navbar-nav')
    ->setMaxDepth(1)
    ->setPartial(array('partial/mynav.phtml', 'Application'))
?&gt;
</pre>
Menu population example:
<pre>
'navigation' => array(
    'admin' => array( 
        'mynav' => array(
            'label' => 'Home',
            'route' => 'home',
            'order' => -1,
            'icon' => 'glyphicon glyphicon-home',
            'pages' => array(
                array( 
                    'label' => 'Page1',
                    'route' => 'application/page1',
                ),
                array( 
                    'label' => 'Page2',
                    'uri'   => '/application/page2', 
                ),
                array( 
                    'label' => 'Page3',
                    'route' => '/application/page3',
                ),
            ),
        ),                        
    ),
)
</pre>
