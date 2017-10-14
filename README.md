#import-export-improvements

## Discuss this PR
Ivan Chepurnyi created this PR at may 2017. It has some very good features in it. We should ask Ivan why development stopped and whats the current status. (https://github.com/magento/magento2/pull/9480)

## Issues in Github (magento/magento2)
https://github.com/magento/magento2/labels/Import%2FExport

## Discussion
### Import Products Categories
PC: When you choose to import CSV with Add/Update the categories will be added to the product. It will not overwrite the currently chosen categories. It seems logic because you choose Add/Update but I think this is not the correct way. The only option at this point you have is to choose Replace but then the whole product is deleted and created again. Which results in a much longer import-time. In my opinion when you import CSV of products you must replace the categories and not add/update them. 
### Importing empty attributes
PC: When you have products with a lot of attributes the column 'additional_attributes' can be huge. It would be better to create new column for each attribute and not combine them in one column. Just like all other attributes. The problem when splitting by character is that you always have to check if your client will not be using that character.
### Automatic create attribute values
PC: When you run import and your value from your attributes hasn't been created you the import will fail. The import should create the attribute values. (not sure yet when multilingual)
### Change the value of visibility
PC: If your Magento2 adminhtml is in dutch the value of the column visiblity must be 'Catalogus, Zoeken' instead of 'Catalog, Search'. When you run CSV by command line the value must be Catalog, Search. We should not use strings but constants or easier, VISIBILITY_NOT_VISIBLE = 1, VISIBILITY_IN_CATALOG = 2, VISIBILITY_IN_SEARCH = 3, VISIBILITY_BOTH = 4.
### Import Related, Upsell SKU
PC: The related, upsell column should be executed after the import. Because when you are importing products and that product doesn't exist yet it will not import that product. Most likely the product will be created later on in that import.
### Import categories multilingual
PC: At this moment it is not possible to import translations of categories by Magnento CSV. (Or I didn't found out yet)
### Imports for clients and for developers
PC: We all agree that Magento2 should add the availability to export CSV and import CSV for their customers. But we 'developers' needs an easier way to import data. Like arrays or XML.
### Examples
PC: Add more examples to Magento2. More complex examples. 

## Available import modules by third-party right now:
* https://github.com/techdivision/import
* https://github.com/firegento/FireGento_FastSimpleImport2
