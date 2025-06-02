# Wesanox Framework Package

A lightweight ProcessWire module for loading essential frontend frameworks (CSS and JS) with minimal setup.  
This module includes common libraries and provides simple methods to output the corresponding `<link>` and `<script>` tags.

---

## Included Frontend Libraries

The following frameworks are bundled and automatically available:

- AOS 2.3.1 (Animate on Scroll)
- Swiper 11.2.6 (Touch slider)
- Bootstrap 5.3.3 (CSS framework)
- jQuery 3.7.1

These files are stored in the module’s internal `styles/` and `scripts/` folders.

---

## Usage

### Output styles:

```php
echo $modules->WesanoxFrameworkPackage->renderStyles();
```

### Output scripts:

```php
echo $modules->WesanoxFrameworkPackage->renderScripts();
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

protected array $scripts = [
    'global_jquery',
    'global_aos',
    'global_swiper',
    'global_bootstrap.bundle',
];
```

> You can customize these lists in your module file to control which assets are included.

---

## File Structure

Files must be named according to this convention:

- CSS: `[name].css` → in `site/modules/WesanoxFrameworkPackage/styles/`
- JS: `[name].js` → in `site/modules/WesanoxFrameworkPackage/scripts/`

Only files that physically exist will be included in the output.

---

## Requirements

- ProcessWire 3.x
- PHP 8.1 or higher

---

## License

GPL-3.0
