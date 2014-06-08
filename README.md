# FieldtypeSelectFile & InputfieldSelectFile

**Inputfield Select File** is an Inputfield & Fieldtype to select a single file or folder and store it. If **Path to files** is omitted in the field settings details tab, the Inputfield will list all files and or folders from the templates folder.

### Settings

The settings for the field are located at the field settings details tab.

* Path to files
* Hide file extensions
* Hide files
* Hide folders

### When to use ?

In the examples I called the field **select_file**.

```php
// let the editor choose a CSS file
$config->scripts->append($config->urls->templates . "scripts/" . $page->select_file);

/**
 * advanced usage example
 *
 * You need multiple ways to render your markup. Let the site editor choose which
 * file the page need to render.
 *
 */

$tpl = new TemplateFile($config->paths->templates . "includes/" . $page->select_file);
$tpl->set('current', $page);
$markup = $tpl->render();

```

![info](https://raw.githubusercontent.com/Da-Fecto/FieldtypeSelectFile/master/images/selectfile.png)
