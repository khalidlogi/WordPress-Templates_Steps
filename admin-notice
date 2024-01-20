## Admin notice function
```php

 $plugin_error = Wpform_gs_Connector_Utility::instance()->admin_notice(array(
         'type' => 'error',
         'message' => 'WPForms Google Sheet Connector Add-on requires WPForms <a href="https://wordpress.org/plugins/wpforms-lite/" target="_blank">(Lite or PRO)</a> plugin to be installed and activated.'
      ));
      echo $plugin_error;

  public function admin_notice($data = array()) {
      // extract message and type from the $data array
      $message = isset($data['message']) ? $data['message'] : "";
      $message_type = isset($data['type']) ? $data['type'] : "";
      switch ($message_type) {
         case 'error':
            $admin_notice = '<div id="message" class="error notice is-dismissible">';
            break;
         case 'update':
            $admin_notice = '<div id="message" class="updated notice is-dismissible">';
            break;
         case 'update-nag':
            $admin_notice = '<div id="message" class="update-nag">';
            break;
         case 'upgrade':
            $admin_notice = '<div id="message" class="error notice wpforms-gs-upgrade is-dismissible">';
            break;
         default:
            $message = __('There\'s something wrong with your code...', 'gsheetconnector-wpforms');
            $admin_notice = "<div id=\"message\" class=\"error\">\n";
            break;
      }

  $admin_notice .= "    <p>" . __($message, 'gsheetconnector-wpforms') . "</p>\n";
      $admin_notice .= "</div>\n";
      return $admin_notice;
   }


```
