# Wesanox Framework Package

A lightweight ProcessWire module for loading essential frontend frameworks (CSS and JS) with minimal setup.  
This module includes common libraries and provides simple methods to output the corresponding `<link>` and `<script>` tags.

---

## Included Frontend Libraries

The following frameworks are bundled and automatically available:

- AOS 2.3.1 (Animate on Scroll)
- Swiper 12.0.2 (Touch slider)
- Bootstrap 5.3.8 (CSS framework)
- Bootstrap Icons 1.13.1 (ICONS from Bootstrap)
- jQuery 3.7.1
- LazyLoad 19.1 (Lazyload images)

These files are stored in the module’s internal `styles/` and `scripts/` folders.

---

## Usage

### Output styles:

```php
echo wire()->modules->WesanoxFrameworkPackage->renderStyles();
```

### Output scripts:

```php
echo wire()->modules->WesanoxFrameworkPackage->renderScripts();
```

These methods generate `<link>` and `<script>` tags for all configured assets **only if the files exist**.

---

## Internal Configuration

The module uses internal arrays to define which files to load:

```php
protected array $styles = [
    'global_aos',
    'global_swiper',
    'global_bootstrap',
];

protected array $styles_scss = [
    'global_bootstrap_icons'
];

protected array $scripts = [
    'global_jquery',
    'global_aos',
    'global_swiper',
    'global_bootstrap.bundle',
    'global_lazyload'
];
```

> You can customize these lists in your module file to control which assets are included.

---

## File Structure

Files must be named according to this convention:

- CSS: `[name].css` → in `site/modules/WesanoxFrameworkPackage/styles/css/`
- SCSS: `[name].scss` → in `site/modules/WesanoxFrameworkPackage/styles/scss/`
- JS: `[name].js` → in `site/modules/WesanoxFrameworkPackage/scripts/`

Only files that physically exist will be included in the output.

---

## Module Configuration

The module settings page allows you to deactivate individual frameworks.
Disabled frameworks will not be output in renderStyles() or renderScripts().

---

## Requirements

- ProcessWire 3.x
- PHP 8.1 or higher

---

## License

GPL-3.0
