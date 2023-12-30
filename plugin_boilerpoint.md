## Include files
```php
Include
private function load_dependencies()
```
## Options 
```php
  $options = [
            'view_option' => 'normal',
            'khdivi_label_color' => '#bfa1a1',
            'khdivi_text_color' => null,
            'khdivi_bg_color' => '#c4c0c0',
            'khdivi_exportbg_color' => '#408c4f',
            'Enable_notification_checkbox' => '0',
            'number_id_setting' => 10,
        ];

        foreach ($options as $option => $default) {
            $value = get_option($option, $default);
            $this->{$option} = $value;
        }
```
