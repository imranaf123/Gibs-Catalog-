# Reusable WhatsApp Catalog

A static, data-driven product catalog with packaging quantities, a saved selection list and a WhatsApp handoff. No prices, accounts or backend are used.

## Preview

Run a static server from this folder, then open its local address:

```sh
python3 -m http.server 8000 --bind 0.0.0.0
```

Visit `http://localhost:8000`. Do not open `index.html` directly; browsers block the JSON fetches on `file://`.

## Add a product

1. Put a 600 × 400 WebP package image in `assets/products/`.
2. Add a unique product object to `data/products.json` with its image path, category, availability and packaging options.
3. Use category IDs from `data/categories.json` and packaging type IDs from `packagingTypes`.
4. Reload the page. Products are ordered as they appear in the JSON array.

## Make another brand

Edit `data/brand.json` (brand ID, name, logo, theme, language, direction and WhatsApp number), then replace the logo and favicon under `assets/brand/`. Update `data/categories.json`, `data/products.json` and `data/i18n/en.json` as needed. Use international digits for the WhatsApp number. The selection is stored separately for each brand ID.

The first six product visuals are local crops from the supplied design reference. Full Carton and Half Carton use plain, unbranded local illustrations; Individual Box reuses the selected product's image. The 14 later product images are locally saved, normalized packaging photos from the official SM Foods bakery page: Crispee Banana, Orange and Strawberry Wafers; JoyStik Chocolate Stick; Makhan Waala Butter Cookies; Zeera Waala Bakery Style Cookies; Coconut Waala Cookies; Tea Time Fine Line Biscuits; Cookiez Pineapple & Coconut Cookies; Crispy Zeera Biscuits; Classic Lemon Sandwich Biscuits; Mango Masti Sandwich Biscuits; Panjeeri Traditional Biscuits; and Milkoney Honey & Milk Biscuits. No external image requests are made at runtime.
