## Download Poeedit
https://drive.google.com/file/d/19aVlkBi50W3IYll3PqAInYvRQYyffPu9/view?usp=drive_link

To create a class for internationalization (i18n) in your plugin, you can define a class that loads the text domain for your plugin. This ensures that your plugin is ready for translation. Here's how you can do it:

## Step 1: Create the i18n Class2. Add the following code to the new file:

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
## Include this new class in your main plugin file and hook it to the plugins_loaded action:
   // Include the i18n class file.
require_once plugin_dir_path( __FILE__ ) . 'includes/class-adas-quote-i18n.php';

// Load the plugin text domain for translation.
add_action( 'plugins_loaded', array( 'Adas_Quote_i18n', 'load_textdomain' ) );

## Step 3: Provide Translation Files
To make your plugin translatable, you need to provide translation files. These files should be placed in the languages directory of your plugin.

Create a new directory named languages in the root of your plugin.
Inside the languages directory, create translation files with the appropriate language codes (e.g., adas_quote_request-fr_FR.mo, adas_quote_request-de_DE.mo, etc.). These files should be generated using a tool like Poedit or the WordPress.org translation platform.
By following these steps, you have set up the i18n functionality for your "Adas Quote for WC" plugin, making it ready for translation and allowing users around the world to use your plugin in their native languages.
