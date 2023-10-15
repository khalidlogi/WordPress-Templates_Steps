##

##

## Tools 

Download [boilerplate](https://www.nexcess.net/blog/wordpress-plugins-getting-started-with-wppb-boilerplate/) files plugin template

Install [WordPress admin plugin](https://github.com/bueltge/WordPress-Admin-Style) 

Create the plugin 

**Enabable debug mode:**

Create debug.log file 

And add the folowing to wp.config:

    // Enable Debug logging to the /wp-content/debug.log file
    define( 'WP_DEBUG_LOG', true );
    // Disable display of errors and warnings
    define( 'WP_DEBUG_DISPLAY', false );
    @ini_set( 'display_errors', 0 );

<!---->

    You can find debug file in 

***

First, you need to create a directory and give it a unique name, then add a PHP file with the same name as the directory. Add the following code the php file that will contain all the info needed for WordPress to display the plugin 

    <?PHP

|                                                                                                                                                                                                                                                                           |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| /\* Plugin Name: kh-stt Plugin URI: https\://kh-test.com/ Description: Plugin to accompany tutsplus guide to creating plugins, registers a post type. Version: 1.0 Author: Rachel McCollin Author URI: https\://kh.com/ License: GPLv2 or later Text Domain: tutsplus \*/ |


##

## Security 

## // restrict direct access here

## defined( 'ABSPATH' ) or die('Can\t Access on this on');

## ***

## include( plugin\_dir\_path( \_\_FILE\_\_ ) . 'ipn/paypal-ipn.php')

##

## Enqueue script 

- ../file.php (file is in the folder that is one level higher than the current directory)

Construct function 

add\_action( 'wp\_enqueue\_scripts', array( $this,'wpse\_load\_plugin\_css' ));

 function wpse\_load\_plugin\_css() {

                $plugin\_url = plugin\_dir\_url( \_\_FILE\_\_ );

           

                wp\_enqueue\_style( 'style1', $plugin\_url . 'css/style1.css' );

                wp\_enqueue\_style( 'style2', $plugin\_url . 'css/style2.css' );

            }

Add wp\_head so that enque style will work 

|                                                                                                                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| add\_action('wp\_enqueue\_scripts','register\_my\_scripts'); function register\_my\_scripts(){ wp\_enqueue\_style( 'style1', plugins\_url( 'css/style1.css' , \_\_FILE\_\_ ) ); wp\_enqueue\_style( 'style2', plugins\_url( 'css/style2.css' , \_\_FILE\_\_ ) ); } |


### Hooks

add\_action('admin\_head','enqueue\_settings\_style'); //Fired at the head section


# Wpdb

Get database name

|                                                                                                                                                                                                            |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| function my\_update\_notice() {    global $wpdb;    ?>    \<div class="updated notice">        \<p>\<?php \_e( "name of Database $wpdb->dbname", 'my\_plugin\_textdomain' ); ?>\</p>    \</div>    \<?php} |


### Show last query

$wpdb->last\_query;

**Show errors**

 echo $wpdb->last\_query ." | " .$wpdb->last\_error;

Insert, replace, and update. 

$wpdb→insert($table, $data, $format) can be used to insert data into the database. Rather than building your own INSERT query, you simply pass the table name and an associative array containing the row data and WordPress will build the query and **escape** it for you. 

The keys of your $data array must map to column names in the table. The values in the array are the values to insert into the table row:

$wpdb->insert( $wpdb->schoolpress\_assignment\_submissions, array( "assignment\_id"=>$assignment\_id, "submission\_id"=>$submission\_id ), array( '%d', '%d' )

);

$wpdb→update($table, $data, $where, $format = null, $where\_format = null ) can be used to update rows in a database table. Rather than building your own UPDATE query, you simply pass the table and an associative array containing the updated columns and new data along with an associative array $where containing the fields to check against in the WHERE clause and WordPress will build the query and escape the UPDATE query for you.

|                                                                                                                                                                                                           |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| $wpdb->update( 'ecommerce\_orders', //table name array( 'status' => 'pending', //data fields 'subtotal' => '100.00', 'tax' => '6.00', 'total' => '106.00'), array( 'id' => $order\_id ) //where fields ); |

|                                                                                                                                                                                                                                                                                                                                                                                                                                |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| $data = array('titre'=> $subject,'name'=> $name , 'ville' =>  $city, 'email'=> $email,'tel'=> $tel,'type1'=> $type1,'type2'=> $type2,'message'=> $message,); $format = array('%s','%s','%s','%s','%s','%s','%s','%s'); //$wpdb->print\_error(); //$wpdb->insert($table,$data,$format); $wpdb->print\_error(); if(isset($id)){     $where = array('id' => $id); $wpdb->update($table,$data, $where,$format); //$wpdb->print; }  |


###

### Delete 

|                                                                           |
| ------------------------------------------------------------------------- |
|  $wpdb->query("DELETE FROM eLearning\_progress WHERE ID = '$user\_id' AND |


### Displaying/hiding SQL errors:

\<?php $wpdb->show\_errors(); ?> 

\<?php $wpdb->hide\_errors(); ?> 

\<?php $wpdb->print\_error(); ?>

if you want to know if query failed

$wpdb -> show\_errors (); $wpdb -> get\_results ($wpdb -> prepare($sql)); $wpdb -> print\_error ();


### Notification notice

$wpdb->insert($table,$data,$format);

echo '\<div class="alert alert-warning alert-dismissible fade show" role="alert">

"'.$wpdb->last\_query.'"\</div>';

Enqueue style

|                                                                                                                                                                                                                                                                                                                                                           |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| /\*----------------------------------------------------------------callstyle\*/ function enqueue\_settings\_style(){ wp\_enqueue\_style( 'enqueue\_settings\_style',plugins\_url( '/css/style.css', \_\_FILE\_\_ )); } add\_action('admin\_print\_styles','enqueue\_settings\_style'); //---------------------------------------------------------------- |


##

## Notice 

[link](https://wpmudev.com/blog/adding-admin-notices/)


## Rederct 

\<?php wp\_redirect( home\_url() ); exit; ?>

***

**Path directory file**

Abslute path: $file\_path = ABSPATH . 'wp-content/';

Require class from another plugin: require\_once(ABSPATH . '/wp-content/plugins/wpforms-lite/wpforms.php');


# Short code 

   

    ob\_start();

    require\_once(plugin\_dir\_path( \_\_FILE\_\_).'html/form.php');

    $content = ob\_get\_contents();

    ob\_end\_clean();

    return $content;

//This code starts by using the `ob_start()` function, which begins output buffering. This means that anything printed or echoed after this point will not be immediately sent to the browser, but instead held in a buffer.

After the file is included and any content it outputs is buffered, the code then gets the current buffer contents using the `ob_get_contents()` function and stores it in a variable called `$content`.

Finally, the buffer is cleared using the `ob_end_clean()` function and the variable `$content` is returned as the result of executing this PHP function.

Overall, this code seems to include the contents of an HTML form from another file and return the resulting HTML as a string. The use of output buffering ensures that only the contents of the included file are captured and not any other output that might occur during the execution of the calling code.

Devide this saperately in HTML and PHP LOGIC, Take a look on this example:

function my\_shortcode() { // Set HTML saperate and return it return include('template/shortcode\_template.php'); }

 Save

**shortcode\_template.php**

|                                                                                                                                                        |
| ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| \<?php ob\_start(); ?> <**strong**>Hi there!\</**strong**> <**p**> This is an include test for shortcodes... \</**p**> \<?php return ob\_get\_clean(); |

**Ps : you have to use RETURN**

**Or use** 

**echo ''?> \<div>\[Whatever HTML you want]\</div> \<?php;**

|                                                                                                                                                                                                                                                                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| function create\_shortcode(){  ob\_start();     return "\<h2>Hello world !\</h2>";  ob\_get\_clean(); } add\_shortcode('my\_shortcode', 'create\_shortcode'); // Use \[my\_shortcode] function create\_shortcode(){     return "\<h2>Hello world !\</h2>"; } add\_shortcode('my\_shortcode', 'create\_shortcode'); // Use \[my\_shortcode] |
|                                                                                                                                                                                                                                                                                                                                            |

Ps :  ob\_get\_clean(); 


# Add option

**get\_option** function is used to retrieve a value from from options table based on option name.

Get\_option second argument, which is by default set to FALSE, is optional.

**_\<?php get\_option( 'my\_text', "I don't have anything written. Yet." ); ?>_**

// Create new option within WordPress

**add\_option**( $option, $value = , $deprecated = , $autoload = 'yes' );


## Create a custom admin settings menu in your Wordpress Dashboard 

|                                                                                                                                                                                           |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| add\_action('admin\_menu','khssettingspage'); function khssettingspage(){ add\_menu\_page( 'kh-settings-page', 'kh-settings', 'manage\_options',  'kh-settings',  'kh-settings-api' ); }; |

|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| \<?php function dbi\_render\_plugin\_settings\_page() {     ?>     <**h2**>Example Plugin Settings\</**h2**>     <**form** action="options.php" method="post">         \<?php          settings\_fields( '[dbi\_example\_plugin\_options](https://docs.google.com/document/d/1lgNskDZtb0CmYsjpMOXKKTIeSl_4HB9EzTcdO3olP_E/edit#bookmark=id.zgeyjs2jd2j7)' );         do\_settings\_sections( 'dbi\_example\_plugin' ); ?>         <**input** name="submit" class="button button-primary" type="submit" value="\<?php esc\_attr\_e( 'Save' ); ?>" />     \</**form**>     \<?php } |

Settings\_fields(‘name-of-settings-group’);

Renders code to tell the form what to as well as well as hidden input (nonce).

You have to register the settings group.

 Do\_settings\_sections

Outputs sections and fields

\<?php

| function dbi\_register\_settings() {// [register\_setting](https://developer.wordpress.org/reference/functions/register_setting/) to create a new record in the [wp\_options](https://deliciousbrains.com/tour-wordpress-database/#wp_options) table for our settings, with ‘dbi\_example\_plugin\_options’ as the option\_name. register\_setting( 'dbi\_example\_plugin\_options', 'dbi\_example\_plugin\_options', '[dbi\_example\_plugin\_options\_validate](https://docs.google.com/document/d/1lgNskDZtb0CmYsjpMOXKKTIeSl_4HB9EzTcdO3olP_E/edit#bookmark=id.n840eiapabyv)' );//the name of the function which handles validating data entered when saving the option.    add\_settings\_section( 'api\_settings', 'API Settings', 'dbi\_plugin\_section\_text', 'dbi\_example\_plugin' );     add\_settings\_field( 'dbi\_plugin\_setting\_api\_key', 'API Key', 'dbi\_plugin\_setting\_api\_key', 'dbi\_example\_plugin', 'api\_settings' );     add\_settings\_field( 'dbi\_plugin\_setting\_results\_limit', 'Results Limit', 'dbi\_plugin\_setting\_results\_limit', 'dbi\_example\_plugin', 'api\_settings' );     add\_settings\_field( 'dbi\_plugin\_setting\_start\_date', 'Start Date', 'dbi\_plugin\_setting\_start\_date', 'dbi\_example\_plugin', 'api\_settings' ); } add\_action( 'admin\_init', 'dbi\_register\_settings' ); |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

|                                                                                                                                                                                                                                                                             |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| \<?php function dbi\_example\_plugin\_options\_validate( $input ) {     $newinput\['api\_key'] = trim( $input\['api\_key'] );     if ( ! preg\_match( '/^\[a-z0-9]{32}$/i', $newinput\['api\_key'] ) ) {         $newinput\['api\_key'] = '';     }     return $newinput; } |

| /\*\* Settings Initialization \*\*/    settings\_error(); to show errors              function myplugin\_settings\_init() { |                                                    |                                                                         |
| :-------------------------------------------------------------------------------------------------------------------------: | -------------------------------------------------- | ----------------------------------------------------------------------- |
|                                   /\*\* Setting section 1. \*\*/    add\_settings\_section(                                 | // add Field to section      add\_settings\_field( |  // Register this field with our settings group.    register\_setting(  |
|                                add\_action( 'admin\_init', '**myplugin\_settings\_init**' );                                |                                                    |                                                                         |


### Sanitize text field by removing HTML tags

Add a function to register settings 

register\_setting( 'myplugin\_settings\_group', 'myplugin\_field\_2',**'saintizfield'**);

function saintizfield($input){

    $output = sanitize\_text\_field( $input );

    return $output;

}

***


### Get plugins 

Include a plugin :

// Check if get\_plugins() function exists. This is required on the front end of the // site, since it is in a file that is normally only loaded in the admin. 

if ( ! function\_exists( 'get\_plugins' ) ) {&#x20;

require\_once ABSPATH . 'wp-admin/includes/plugin.php'; } 

$all\_plugins = get\_plugins(); 

// Save the data to the error log so you can see what the array format is like. error\_log( print\_r( $all\_plugins, true ) );

/\*\* \* Detect plugin. For use on Front End and Back End. \*/ 

// check for plugin using plugin name 

if(in\_array('plugin-directory/plugin-file.php', 

apply\_filters('active\_plugins', get\_option('active\_plugins')))){&#x20;

//plugin is activated 

}

if (in\_array('wpforms-lite/wpforms.php', apply\_filters('active\_plugins', get\_option('active\_plugins')))) {

                //plugin is activated

                error\_log('wpform is active');

            }
