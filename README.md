# Nesst food packs

Per-country food product packs used by the Nesst app for offline food search.
Each `<cc>.db` is a read-only SQLite file holding the most-scanned products sold in
that country (name, brand, barcode, kcal, protein, carbohydrate, fat per 100 g,
serving size, and the micronutrients food labels state: fibre, sugars, saturated,
mono- and polyunsaturated fat, omega-3, cholesterol, sodium, calcium, iron, potassium,
vitamin D). `index.json` lists every pack with its build time and SHA-256.

## Source and licence

The data comes from **[Open Food Facts](https://world.openfoodfacts.org)**, a
collaborative, free and open database of food products.

These packs are a derived database of Open Food Facts and are made available under the
**[Open Database License (ODbL) v1.0](https://opendatacommons.org/licenses/odbl/1-0/)**.
Individual contents are under the
[Database Contents License (DbCL) v1.0](https://opendatacommons.org/licenses/dbcl/1-0/).
Product images are not included.

Changes from the source: only products with complete energy and macronutrient values
pass; values that are physically impossible or whose energy disagrees with
4·protein + 4·carbohydrate + 9·fat by more than 20 % are dropped; other vitamins and
minerals are left out, since most of them are estimated from ingredient lists rather than
read from a label; five or more vitamin/mineral zeros on one product are treated as blanks;
each country keeps its 50,000 most-scanned products.

Built by `tools/food/build.mjs` in the Nesst app repository.
