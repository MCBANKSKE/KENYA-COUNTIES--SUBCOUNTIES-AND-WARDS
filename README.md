# Kenya Administrative Units Database

A comprehensive database of Kenya's administrative units including Counties, Subcounties, and Wards. This project provides a structured and easily accessible way to work with Kenya's administrative divisions in your Laravel application.

## Features

- Complete list of all 47 Kenyan Counties
- Comprehensive Subcounty data
- Ward information for each Subcounty
- Laravel Eloquent models with relationships
- Database seeders for easy setup

## Data Structure

The database includes the following main entities:

### County
- `id` - Unique identifier
- `county_name` - Name of the county

### SubCounty
- `id` - Unique identifier
- `county_id` - Reference to the parent county
- `constituency_name` - Name of the constituency
- `ward` - Name of the ward
- `alias` - Alternative name or alias (if any)

## Installation

1. Clone this repository
2. Copy the database files to your Laravel project's database directory
3. Run migrations:
   ```
   php artisan migrate
   ```
4. Seed the database:
   ```
   php artisan db:seed
   ```

## Usage

### Accessing Data

```php
// Get all counties
$counties = \App\Models\County::all();

// Get subcounties for a specific county
$county = \App\Models\County::find(1);
$subcounties = $county->subcounties;

// Get all wards in a specific subcounty
$wards = \App\Models\SubCounty::where('constituency_name', 'Westlands')->get();
```

### Relationships

The models include the following relationships:

- A County has many SubCounties
- A SubCounty belongs to a County

## Data Sources

The administrative data is based on the official Kenyan administrative boundaries and has been structured for use in web applications.

## Contributing

Contributions are welcome! If you find any issues or have suggestions for improvements, please open an issue or submit a pull request.

## License

This project is open-sourced under the [MIT License](LICENSE).

## Support

For support, please open an issue in the repository.

---

*Last updated: May 2025*
