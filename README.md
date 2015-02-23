# FieldtypeSelectFile & InputfieldSelectFile

**Inputfield Select File** is an Inputfield & Fieldtype to select a single file or folder and stores the name and / or use the selected file as page template.

### Settings

* The folder containing the files and/or folders.
    - A relative path relative to the /site/templates/ folder.
* Hide file extensions
* Hide files
* Hide folders
* Natural Sort (Select options)
    - Sort files and folders in natural ordering (PHP >= 5.4.0)
* Change Page Template
    - Just before the **Page::loaded** event the selected file is set as template file for the page. This setting can only be applied once per a page and folders are exluded from the select inputfield.

    Note that a page with no associated template file will render with the selected file.


### When to use ?

Let editors select a file and base your own logic upon this. With the __change page template__ setting you're able to  use the selected file as template file. This could reduce the amount of normal templates needed and let editors choose how the page get rendered. It could be a real good companion with InputfieldSelector there are plenty of use cases for this Inputfield.


In the examples I call the field **selected_file**.

```php
// let the editor choose a CSS file
$config->scripts->append($config->urls->templates . "scripts/" . $page->selected_file);

/**
 * advanced usage example
 *
 * You need multiple ways to render your markup. Let the site editor choose which
 * file the page need to render.
 *
 */

$tpl = new TemplateFile($config->paths->templates . "includes/" . $page->selected_file);
$tpl->set('current', $page);
$markup = $tpl->render();

```
