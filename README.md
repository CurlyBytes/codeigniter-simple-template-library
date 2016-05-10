
# Simple Template Library for Codeigniter

The simplest template libary for Codeigniter ever. The code is easy to understand and modify it for your needs.

### Installation

Download library.php to your library folder.

```php
$this->load->library(array('layout'));
```
Put **CI_head()** inside **&lt;head&gt;** and **&lt;/head&gt;** tag in view.
```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="utf-8">
	<meta http-equiv="X-UA-Compatible" content="IE=edge">
	<title><?= $title ?></title>
	<?= CI_head() ?>
</head>
```

Put **CI_footer()** before **&lt;/body&gt;** tag in view.
```html
<?= CI_footer() ?>
</body>
</html>
```

### API Examples
Use the following APIs in controller.


####add_meta
add_meta($name, $value, $type = 'meta')

####add_css_file
add_css_file($tag_css, $path = '')

####add_css_files
add_css_files($tag_css = array(), $path = '')

```php
$this->layout->add_css_files(array('bootstrap.min.css','style.css'), base_url().'assets/css/');
```
Output
```html
    <link href="http://dictpedia.org/assets/css/bootstrap.min.css" rel="stylesheet" />
    <link href="http://dictpedia.org/assets/css/style.css" rel="stylesheet" />
```

####add_css_rawtext
add_css_rawtext ( string $content )
```php
/*
 * @param string $content
 */
 
$css_text = <<<EOF

.text {
	font-size: 12px;
	background-color: #eeeeee;
}
EOF;
		$this->layout->add_css_rawtext($css_text);
		
	}
```
Output
```html
<style>


.text {
	font-size: 12px;
	background-color: #eeeeee;
}

</style>
```

####add_js_file
add_js_file ( string $tag_js , string $path, string $position )

```php
$this->layout->add_css_file('https://ajax.googleapis.com/ajax/libs/jquery/1.11.2/jquery.min.js');
```
Output
```html
	<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.2/jquery.min.js"></script>
```

####add_js_files
add_js_files ( array $tag_js , string $path, string $position )

```php
$this->layout->add_css_files(array('bootstrap.min.js','script'), base_url().'assets/js/');
```
Output
```html
	<script src="http://dictpedia.org/assets/js/bootstrap.min.js"></script>
	<script src="http://dictpedia.org/assets/js/script.js"></script>
```

####add_js_rawtext
add_js_rawtext ( string $content , string $position )

```php
/*
 * @param string $content
 * @param string $position - 'header' or 'footer'
 */
 
$js_text = <<<EOF
alert('this is just a test');
EOF;
	$this->layout->add_js_rawtext($js_text, 'header');
		
}
```

Output
```html
<script>

alert('this is just a test');

</script>
```
