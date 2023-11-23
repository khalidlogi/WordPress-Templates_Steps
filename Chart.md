# WordPress Chart widget
## enqueue 
```php

add_action('admin_enqueue_scripts', array($this, 'khwpforms_enqueue_dashboard_widget_scripts'));

function khwpforms_enqueue_dashboard_widget_scripts()
        {

            wp_enqueue_script( 'chartjs', 'https://cdnjs.cloudflare.com/ajax/libs/Chart.js/2.5.0/Chart.min.js' );

            //wp_enqueue_script('khwpforms_dashboard_widget_script', plugin_dir_url()() . '/dashboard-widget.js', ['chart-js'], false, true);
        }

//Display
add_action('wp_dashboard_setup', array($this, 'register_first_custom_dashboard_widget'));

 function register_first_custom_dashboard_widget()
        {
            wp_add_dashboard_widget(
                'my_first_custom_dashboard_widget',
                'My Custom Dashboard Widget',
                array($this, 'my_first_custom_dashboard_widget_display')
            );

        }

  function my_first_custom_dashboard_widget_display()
        {
            global $wpdb;
            $table_name = $wpdb->prefix . 'wpforms_db2';

            $results = $wpdb->get_results("SELECT DATE(form_date) AS date, COUNT(*) AS count FROM $table_name 
            GROUP BY DATE(form_date)", ARRAY_A);
            $dates = array_column($results, 'date');
            $counts = array_column($results, 'count');

            error_log(print_r($dates, true));
            //var_dump(print_r($counts, true));
            ?>
<canvas id="myChart"></canvas>
<script>
var ctx = document.getElementById('myChart').getContext('2d');
var myChart = new Chart(ctx, {
    type: 'bar',
    data: {
        labels: <?php echo json_encode($dates); ?>,
        datasets: [{
            label: '# of Entries',
            data: <?php echo json_encode($counts); ?>,
            backgroundColor: 'rgba(75, 192, 192, 0.2)',
            borderColor: 'rgba(75, 192, 192, 1)',
            borderWidth: 1
        }]
    },
    options: {
        scales: {
            y: {
                beginAtZero: true
            }
        }
    }
});
</script>
<?php
        }

```
