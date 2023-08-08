# WordPress-Templates_Steps

```<?php
/*
Plugin Name: PL1

Plugin URI: https://kh-test.com/

Description: Plugin to accompany tutsplus guide to creating plugins, registers a post type.

Version: 1.0

Author: Rachel McCollin

Author URI: https://kh.com/

License: GPLv2 or later

Text Domain: tutsplus

*/





if(! defined('ABSPATH')){
    exit;
}

if(!class_exists('MYCLASS')){
    class MYCLASS{
        function __construct() {
        $this->defineconstants();
        register_deactivation_hook( __FILE__, array( $this, 'deactivate' ));
        register_activation_hook( __FILE__, array( $this, 'activate') );


        }

        public function defineconstants(){
            define('mypath',plugin_dir_path( __FILE__ ));
            define('myurl',plugin_dir_url( __FILE__ ));
            define('myversion','1.0.0');

        }
        public function createbd(){
            
        }

        public  function activate(){
            global $wpdb;
            $plugin_name_db_version = '1.0';
            $table_name = $wpdb->prefix . "devis"; 
            $charset_collate = $wpdb->get_charset_collate();
            
            $sql = "CREATE TABLE $table_name (
                      id mediumint(9) NOT NULL AUTO_INCREMENT,
                      created timestamp NOT NULL default CURRENT_TIMESTAMP,
                      name tinytext NULL,
                      ville varchar(255) DEFAULT '' NOT NULL,
                      email varchar(255) DEFAULT '' NOT NULL,
                      UNIQUE KEY id (id)
                    ) $charset_collate;";
            
            require_once( ABSPATH . 'wp-admin/includes/upgrade.php' );
            dbDelta( $sql );
            add_option( 'plugin_name_db_version', $plugin_name_db_version );

        }

        public  function deactivate(){
            global $wpdb;
            $table_name = $wpdb->prefix . "devis"; 
            $wpdb->query("DROP TABLE IF EXISTS  $table_name");
            
            require_once( ABSPATH . 'wp-admin/includes/upgrade.php' );
           // dbDelta( $sql );
           echo "Deactivated $table_name deleted";
        }

        public static function uninstall(){

        }
    }


}

if(class_exists('MYCLASS')){
//    register_activation_hook( __FILE__, 'MYCLASS::activate') ;
  //  register_deactivation_hook( __FILE__, 'MYCLASS::deactivate');
    register_uninstall_hook( __FILE__, 'MYCLASS::uninstall' ); //call back should be static 
$myclass = new MYCLASS(); // call the class 
}
```
