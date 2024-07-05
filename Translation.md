To create a class for internationalization (i18n) in your plugin, you can define a class that loads the text domain for your plugin. This ensures that your plugin is ready for translation. Here's how you can do it:

1. Create a new file named `class-adas-quote-i18n.php` in the `includes` directory.
2. Add the following code to the new file:

   ```php
   <?php
   /**
    * Class for handling internationalization (i18n) for the Adas Quote for WC plugin.
    *
    * @package AdasQuoteForWC
    */

   if ( ! defined( 'ABSPATH' ) ) {
       exit; // Exit if accessed directly.
   }

   class Adas_Quote_i18n {

       /**
        * Load the plugin text domain for translation.
        */
       public static function load_textdomain() {
           load_plugin_textdomain(
               'adas_quote_request',
               false,
               dirname( plugin_basename( __FILE__ ) ) . '/languages/'
           );
       }
   }

   ```
   Include this new class in your main plugin file and hook it to the plugins_loaded action:
   // Include the i18n class file.
require_once plugin_dir_path( __FILE__ ) . 'includes/class-adas-quote-i18n.php';

// Load the plugin text domain for translation.
add_action( 'plugins_loaded', array( 'Adas_Quote_i18n', 'load_textdomain' ) );
