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

## View of a Magento Solution Partner

As one of the leading german solution partners, we've Magento 1 + 2 import issues in all projects with > 100.000 products. The core import/export functionality provided by Magento 1, as well as Magento 2, is very complex and hard to extend/maintain. We think it'll be very helpful for all Developers working on bigger Magento projects, when Magento, together with the Community, will provide a well designed, higly flexible, extensible and performant import/export functionality.

### What would be the appropriate scope?

One of the project scopes should be

* That the basic functionality finally is part of the Magento core in any way
* Import/Export plugins can be up-/downloaded from the Magento Marketplace (like other extensions)

In this scenario, plug-in's provide something like import/export adapters for the main ERP, PIM, OMS and many other third party solutions, that can easily integrated within project scope. Additionally, it would be very helpful, if all solution partners will share their extension specific import/export customizations of the third party extensions, they used in their projects, e. g. an import adpater for the Magic360 extension to allow importing 360 images also.

Altogether this approach will result in something like a very flexible import/export platform for Magento which can easily be extended with with plugins from the marketplace.

### What is the necessary functionality?

Parts of the functionality that is needed for bigger projects will already be provided by the Magneto core functionality, for sure. In most cases, this functionality is **NOT** enough which requires a whole lot of time and costs for our customers to extend/improve it.   

#### Which entity types should be supported?

At least, the functionality that should be provided the import/export of

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

#### What looks the basic functionality like?

Beside the possiblity to import the main [entity types](#which-entity-types-should-be-supported), basic functionality for us means

* Import/Export History
* Execute by a Timer Service, e. g. CRON
* Start/Stop/Resume running jobs
* Avoid concurring imports (e. g. using pipelines)
* Archiving import artefacts (including log files)
* Handle multiple import files per import (bunches)
* Flag/OK file or other mechanism to mark import ready-to-go

> Finally and, in our case propably the most important feature is, **NOT** to restricted the import/export to one process (which prevents it from utililization of all CPU cores if possible/necessary) to make sure, that [performance/memory](#what-performancememory-requirements-do-we-have) targets can be fulfilled.

#### How should the functionality be integrated?

The functionality should be available by the

* CLI 
* Backend
* API

### What Performance/Memory requirements do we have?

Performance and memory consumption **MUST** be on an acceptable level. This means, that the import of 100.000+ SKUs should run > 10 minutes on a up-to-date system, with at least 4 Cores and 8 GB RAM. 

Import/Export performance **MUST NOT** go down with a raising number of SKUs. 

The memory consumption **MUST NOT** continually raise during the import, but should stop at a configurable peek to make sure that the available resources are **NOT** exeeded.

> Finally performance/memory requirements, as well as the other topics, needs a lot more discussion. But this could be a very good base for discussions and will hopefully result in one of the next community projects, after the MSI.
