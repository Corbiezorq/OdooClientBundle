OdooClientBundle
================

OdooClientBundle is an Odoo client for Symfony 2. It is inspired on [OpenERP API][1] from simbigo and uses a more or less similar API. Instead of an own XmlRpc client it depends on the fxmlRpc (https://github.com/lstrojny/fxmlrpc).

This is a fork of https://github.com/jacobsteringa/OdooClient . It has no dependecies to Zend. 

Installation
------------

Add bundle to KernelApp.php, e.g.

    $bundles[] = new Clicktrend\Bundle\OdooClientBundle\ClicktrendOdooClientBundle(),

Usage
-----
	
	use Clicktrend\Bundle\OdooClientBundle\Client\Odoo;

    $webservice = new Odoo($endpoint, $database, $username, $password);

    $condition = array(
        array('sale_ok', '=', 'TRUE')
    );
    
    $result = $webservice->search('product.template', $condition, $offset, $limit);
    $products = $webservice->read('product.template', $result);


Todo
----

* Create Dependency Injection to create client from config.yml

[1]: https://bitbucket.org/simbigo/openerp-api