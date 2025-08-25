
# WooCommerce CSV Cleaning Documentation

## Overview
This process cleans and formats a raw CSV file containing product data so that it can be directly imported into WooCommerce.

## Problems in the Raw File
- First row contained unnecessary headers, not actual column names.
- Price fields contained the `€` symbol, which WooCommerce does not accept.
- Several empty columns were present, cluttering the dataset.
- Data needed to be aligned with WooCommerce's standard columns.

## Steps Taken
1. Load the CSV file and use the **second row** as the header row.
2. Remove all Euro (`€`) symbols from numeric fields.
3. Drop any completely empty columns.
4. Keep only relevant WooCommerce columns, such as:

   - `ID`  
   - `Typ`  
   - `Artikelnummer (SKU)`  
   - `Name`  
   - `Veröffentlicht`  
   - `Ist hervorgehoben?`  
   - `Sichtbarkeit im Katalog`  
   - `Kurzbeschreibung`  
   - `Beschreibung`  
   - `Steuerstatus`  
   - `Vorrätig?`  
   - `Lieferrückstände erlaubt?`  
   - `Nur einzeln verkaufen?`  
   - `Kundenrezensionen erlauben?`  
   - `Regulärer Preis`  
   - `Kategorien`  
   - `Bilder`  

5. Save the cleaned file as a **UTF-8 CSV** with `,` as the delimiter.

## Result
The output file `woocommerce_products_clean.csv` is WooCommerce-compatible and ready for import.

## Prompt Used
The following prompt was given to process the file:

```
Format this the right way removing euro sign, deleting top row thats not necessary and everything to make it run on woocommerce, make sure it reads everything like categories, availability description and other data available on the doc
```

This ensured the file was cleaned and structured according to WooCommerce requirements.
