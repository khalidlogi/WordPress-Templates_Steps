# Font Awesome
```php

Create files:
webfonts
\assets\css\font-awesome.css
<i class="fas fa-trash"></i></button>';

wp_enqueue_style('font-awesome', plugin_dir_url(__FILE__) . '/assets/css/font-awesome.css');
OR
wp_enqueue_style('font-awesome', 'https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css', array(), '5.15.3');
           
```
