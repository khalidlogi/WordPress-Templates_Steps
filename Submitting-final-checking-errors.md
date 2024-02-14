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

## codesniffer
https://github.com/PHPCSStandards/PHP_CodeSniffer/
