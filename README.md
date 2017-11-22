#import-export-improvements

## Discuss this PR
Ivan Chepurnyi created this PR at may 2017. It has some very good features in it. We should ask Ivan why development stopped and whats the current status. (https://github.com/magento/magento2/pull/9480)

## Issues in Github (magento/magento2)
https://github.com/magento/magento2/labels/Import%2FExport

## Available import modules by third-party right now:
* https://github.com/techdivision/import-cli-simple
* https://github.com/firegento/FireGento_FastSimpleImport2
* https://github.com/ho-nl/magento2-Ho_Import
* http://www.unirgy.com/products/urapidflow
* https://github.com/Agence-DnD/PIMGento-2
* https://github.com/firebearstudio/importexportfree

## Requested Improvements (from a Solution Partner)

As one of the leading german solution provider we've Magento 1 + 2 import issues in all projects with > 100.000 products. The core import/export functionality provided by Magento 1, as well as Magento 2, is very complex and hard to extend/maintain. We think it'll be very helpful for all Developers working on bigger Magento projects, when Magento, together with the Community, will provide a well designed, higly flexible, extensible and performant import/export functionality.

One of the project scopes should be, that the basic functionality is part of the Magento core, but as on Magento Marketplace, specific extensions for the core can easily downloaded and integrated. Therefore, we think of extensions for ERP, PIM, OMS and many other third party solutions on the one hand. On the other hand vendors of Magento extensions can easily extend their extensions with the necessary functionality to support import/export functionality.

### Functionality

Parts of the functionality that is needed for bigger projects is already provided by the Magneto core functionality. In most cases, this functionality is **NOT** enough which requires a whole lot of time and costs for our customers to extend/improve it.   

#### Entity Types

At least, the functionality that should be provided is to import/export

* Products
  - All Product Types
  - Product Relations (Upsell, Crosssell + Related)
  - Media Gallery
  - Inventory
  - Pricing
* Categories
* Attributes
* Attribute Sets
* Attribute Groups
* Customers

#### Basic Functionality

Beside the possiblity to import the main [entity types](), basic functionality for us means

* Import history
* Execute by a timer service, e. g. CRON
* Start/Stop/Resume running jobs
* Avoid concurring imports (pipelines)
* Archiving import artefacts (including log files)
* Handle multiple import files per import (bunches)
* Flag/OK file or other mechanism to mark import ready-to-go

> Finally and, in our case propably the most important feature: **NOT** restricted to one process (to utililize all CPU cores if possible/necessary) to make sure, that performance/memory targets can be reached.

#### Integrations

The functionality should be integrated into

* CLI 
* Backend
* API

### Performance/Memory

Performance and memory consumption **MUST** be on an acceptable level. This means, that the import of 100.000+ products should run > 10 minutes on a up-to-date system, with at least 4 Cores and 8 GB RAM.

The memory consumption should **NOT** continually raise during the import, but should stop at a configurable peek to make sure that the available resources are **NOT** exeeded.   
