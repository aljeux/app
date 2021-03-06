Phundament 3 App
================

Upgrade Guide
-------------

### Upgrading from v0.10.x

Shell

`./yiic p3bootstrap`

`config/console.php`

        'p3pages' => array(
            'class' => 'vendor.phundament.p3pages.P3PagesModule',
            'params' => array(
                'availableLayouts' => array(
                    '//layouts/main' => 'Main Layout',
                    '_TbNavbar' => '_TbNavbar (Top-Menu Container)'
                ),
                'availableViews' => array(
                    '//p3pages/column1' => 'One Column',
                    '//p3pages/column2' => 'Two Columns',
                )
            ),
        ),

        'rights' => array(
            'class' => 'application.vendor.crisu83.yii-rights.RightsModule',
            'cssFile' => '/themes/backend/css/yii-rights.css'
        ),

### Upgrading from v0.9.x

`composer.json`

`"require"`

        "crisu83/yii-rights": "@dev",
        "mishamx/yii-user": "dev-master as 0.3.999",
        "yiiext/migrate-command": "@dev",
        "vitalets/yii-bootstrap-editable": "dev-master as 1.0",
        "phundament/jquery-file-upload": "dev-master as 0.0.1"

`"require-dev"`

        "phundament/lessii": "master@dev",
        "crisu83/yii-less": "dev-tip as 0.0.1"        

Legacy package repository for 0.9.x versions: `http://packages.phundament.com/0.9/`


### Upgrading from v0.8.x

#### config/console.php

`composer.callbacks`

     'phundament/p3admin-install' => array('yiic', 'p3webapp', 'create', realpath(dirname(__FILE__) . '/..'), 'git', '--interactive=0'),
     
### Upgrading from v0.7.x

#### config/main.php

`import`
    
    'application.vendor.vitalets.yii-bootstrap-editable.*', // p3media

Extension used in p3media-0.8.

`modules.p3media.presets`

    'p3media-manager' => array(
        'commands' => array(
            'resize' => array(300, 200),
        ),
        'type' => 'png'
    ),

Preset used in manager view in p3media-0.8