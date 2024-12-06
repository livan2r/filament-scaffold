# Filament Scaffold

[![Latest Version on Packagist](https://img.shields.io/packagist/v/solution-forest/filament-scaffold.svg?style=flat-square)](https://packagist.org/packages/solution-forest/filament-scaffold)
[![Total Downloads](https://img.shields.io/packagist/dt/solution-forest/filament-scaffold.svg?style=flat-square)](https://packagist.org/packages/solution-forest/filament-scaffold)

## Description
Filament scaffold is a toolkiit for Filament Admin that simplifies the generation of resources. It can automatically generate models, resources, migration files, and more, creating corresponding forms and table views based on the database table. Filament scaffold aims to speed up development and reduce the time spent writing repetitive code.

## Features
- Automatic Filament Resource Generation: Generates Filament resource files, including forms and table views, based on specified table names.

- Support for Multiple Artifact Types: Can generate models, migration files, factories, controllers, and more.

- Dynamic Form Generation: Automatically generates form fields based on database table structure.

- Seamless Integration with Laravel and Filament: Utilizes Laravel's Artisan commands and Filament's extension mechanism for efficient resource management.

## Installation
You can install the package via composer:
```bash
composer require solution-forest/filament-scaffold
```

Then, you need to connect to the database in the .env file.

In your preject, app\Providers\Filament\xxxPanelProvider.php add this code:
```bash
use Solutionforest\FilamentScaffold\FilamentScaffoldPlugin;

public function panel(Panel $panel): Panel
    {
        return $panel
            ..., 
            ->plugin(FilamentScaffoldPlugin::make());
    }
```

## Publishing Configuration file
To publish the configuration file, use:
```bash
php artisan vendor:publish --provider="Solutionforest\FilamentScaffold\FilamentScaffoldServiceProvider" --tag="filament-scaffold-config"
```
You can turn to false to unable the form.
```bash
return [
    'enabled' => false,
];
```

## Usage
In your admin page will have a Scaffolds from. You can choose the table from the connected database or create other table in the form. Then, you can click the "Create" button to create the reesource, model or migration.

> [!NOTE]
> In the resource file, for the table, the table column type default is TextColumn. For the form, the type defualt is TextInput.

## Preview

https://github.com/user-attachments/assets/adb41e0c-df7c-48cf-8d33-d5e7d985efb7

![image](https://github.com/user-attachments/assets/48aaee63-f46c-4d9f-b6d1-0539384b2538)

![image](https://github.com/user-attachments/assets/6c8cdc4b-1330-487a-acab-17cf94f93f82)
![image](https://github.com/user-attachments/assets/c5f6a10f-139d-4344-b135-59f3d18acb30)
![image](https://github.com/user-attachments/assets/37872ba4-00f8-414f-a041-f7ab10cef1a8)
![image](https://github.com/user-attachments/assets/af177dd6-8382-42d7-b5cd-b5b1e97ed753)

## Changelog

Please see [CHANGELOG](CHANGELOG.md) for more information on what has changed recently.

## Contributing

Please see [CONTRIBUTING](.github/CONTRIBUTING.md) for details.

## Security Vulnerabilities

Please review [our security policy](../../security/policy) on how to report security vulnerabilities.

## Credits

- [celia514](https://github.com/solutionforest)
- [All Contributors](../../contributors)

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.
