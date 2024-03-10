### check all __ $ and escape all outputs 
search fro printf echo sprintf __ , and make sure they are all escaped

### Date
replace date by gmdate() to avoid timezone conflict

### isset
if (isset($_POST['id'])) {
    $id = intval($_POST['id']);
    // Rest of your code...
}

### sanitize
sanitize_text_field $_post['nonce']

## escaping
// phpcs:ignore WordPress.Security.EscapeOutput.OutputNotEscaped -- XSS OK.
// phpcs:ignore WordPress.DB.DirectDatabaseQuery.NoCaching
 WordPress.DB.PreparedSQLPlaceholders.UnfinishedPrepare

### direct : 
// phpcs:ignore WordPress.DB.DirectDatabaseQuery

### ignore caching and direct: 		
// phpcs:ignore WordPress.DB.DirectDatabaseQuery.DirectQuery, WordPress.DB.DirectDatabaseQuery.NoCaching		


## codesniffer
phpcs --standard=WordPress --extensions=php --ignore=vendor C:\laragon\www\wp-content\plugins\adas
## vs code:
@id:editor.defaultFormatter @lang:php formatted
instal phpc formatted

phpcs --version
istall wordpess coding standard:
composer global require wp-coding-standards/wpcs

run error checks:
phpcs --standard=WordPress .

scan a file:
phpcs --standard=WordPress path/to/your/file.php


https://github.com/PHPCSStandards/PHP_CodeSniffer/

## phpcomtability

error stating that the "PHPCompatibility" coding standard is not installed in PHPCS
composer global require "phpcompatibility/php-compatibility"

phpcs -p . --standard=PHPCompatibility --runtime-set testVersion 8.2




