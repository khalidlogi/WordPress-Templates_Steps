# WordPress Chart widget
## enqueue 
```php

add_action('admin_enqueue_scripts', array($this, 'khwpforms_enqueue_dashboard_widget_scripts'));

function khwpforms_enqueue_dashboard_widget_scripts()
        {

            wp_enqueue_script( 'chartjs', 'https://cdnjs.cloudflare.com/ajax/libs/Chart.js/2.5.0/Chart.min.js' );

            //wp_enqueue_script('khwpforms_dashboard_widget_script', plugin_dir_url()() . '/dashboard-widget.js', ['chart-js'], false, true);
        }

```
