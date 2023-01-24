# CakePHP Pluginception

A demo application to try out loading plugins as a whole in `Application.php` vs. creating a stand-alone plugin which contains all the dependencies in itself.

## Loading plugins

### To load EE plugins

- Change `composer.json` file to `pluginception/ee`
- Run `composer update pluginception/ee` (without it composer won't able to resolve the classes)
- Uncomment `$this->addPlugin(\Pluginception\Ee\EePlugin::class);` (line no. 67) and comment out `$this->addPlugin(\Pluginception\Ce\CePlugin::class);` (line no. 66) in `src/Application.php` file.

The EE plugin will load all the CE, all the plugins of CE plugin(see `plugins/Ce/plugins`), EE plugin itself and all the plugins of EE plugin(see `plugins/Ee/plugins`).

https://giphy.com/explore/inception

### To load CE plugins

Do the inverse of what you did to load EE, Duh!

## References

- https://stackoverflow.com/a/70184257/3370200
- https://getcomposer.org/doc/05-repositories.md#path
- https://getcomposer.org/doc/articles/troubleshooting.md#i-have-a-dependency-which-contains-a-repositories-definition-in-its-composer-json-but-it-seems-to-be-ignored-
