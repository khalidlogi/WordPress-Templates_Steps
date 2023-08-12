## template for the main php file 👧 
```php

class Tablesome_Plugin
        {
            private static $instance;
            public static function get_instance()
            {
                if (!isset(self::$instance) && !self::$instance instanceof Tablesome_Plugin) {
                    self::$instance = new Tablesome_Plugin();
                    self::$instance->init();
                }
                return self::$instance;
            }

            public static function init()
            {
                ini_set('memory_limit', '2048M');
                self::$instance->setup_constants();
                self::$instance->tablesome_activation();
                add_action('plugins_loaded', array(self::$instance, 'tablesome_load_textdomain'));
                require_once plugin_dir_path(__FILE__) . "/includes/lib/freemius-integrator.php";
            }

            public static function setup_constants()
            {

                $constants = [
                    'TABLESOME_VERSION' => '1.0.16',
                    'TABLESOME_DOMAIN' => 'tablesome',
                    'TABLESOME_CPT' => 'tablesome_cpt',
                    'TABLESOME__FILE__' => __FILE__,
                    'TABLESOME_PLUGIN_BASE' => plugin_basename(__FILE__),
                    'TABLESOME_PATH' => plugin_dir_path(__FILE__),
                    'TABLESOME_URL' => plugins_url('/', __FILE__),

                    /** Storing Settings Options in Database tables feilds using CS_Framework*/
                    'TABLESOME_OPTIONS' => 'tablesome_options',
                    'TABLESOME_CUSTOMIZE_OPTIONS' => 'tablesome_customize_options',
                    'TABLESOME_SAMPLE_TABLE_OPTION' => 'tablesome_sample_table_id',

                    'TABLESOME_INSIGHTS_DATA_OPTION' => 'tablesome_insights_data',

                    /** Storing table records */
                    'TABLESOME_RECORDS_TABLE_NAME' => 'tablesome_records',

                    'TABLESOME_TABLE_NAME' => 'tablesome_table',

                    /** policies */
                    'TABLESOME_MAX_RECORDS_TO_READ' => 10000,
                    'TABLESOME_MAX_COLUMNS_TO_READ' => 25,
                    'TABLESOME_BATCH_SIZE' => 2000,

                    /*** pagination */
                    'TABLESOME_NO_OF_RECORDS_PER_PAGE' => 10,

                    /** CRON interval value key  */
                    'TABLESOME_SCHEDULE_INTERVAL' => 'tablesome_data_test_interval',

                    'TABLESOME_COPY_RECORDS_LIMIT' => 1000,

                    'TABLESOME_ALIAS_PREFIX' => 'ts_',

                    'TABLESOME_CONNECTOR_DOMAIN' => "https://api.tablesomewp.com",
                ];

                foreach ($constants as $constant => $value) {
                    if (!defined($constant)) {
                        define($constant, $value);
                    }
                }
            }
    public static function tablesome_activation()
            {
                if (!version_compare(PHP_VERSION, '5.4', '>=')) {
                    add_action('admin_notices', [self::$instance, 'tablesome_fail_php_version']);
                } elseif (!version_compare(get_bloginfo('version'), '4.5', '>=')) {
                    add_action('admin_notices', [self::$instance, 'tablesome_fail_wp_version']);
                } else {
                    require plugin_dir_path(__FILE__) . 'includes/plugin.php';
                }
            }

```
