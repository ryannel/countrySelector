# Country Selector
This country selector was written to be easy to use and to have no dependencies.

# Getting started
In order to use the Country Selector you must first include the countries.js file. The countries.min.js file has been minified to make it as small as possible and should be used for production. 

This can be done by placing the following script tag at the bottom of your HTML, just before the closing body tag.
```html
// Load the country selector file.
<script src="countries.min.js"></script>

</body>
</html>
```

Now that the file has been included you will be able to access the country selector methods by calling window.countrySelector. Before calling any methods you need to ensure that all content has loaded and that the select boxes you want to populate have been placed on screen.

You can ensure that this has happened by placing your function calls in a window.onload event listener

```html
<script>
    // Onload event is triggered once all content has been loaded.
    window.onload = function () {
    	// Populate and link country and region select with the ID of 'countries'
    	countrySelector.countrySelect('countries');
    };
</script>
```

# Demos
If you would like to see a working example please see the demo folder alongside this file. Once you have selected a demo you can run it by opening the **index.html** file.

If you would like a quick start guide, the demos should have enough information to get you started without reading all the documentation.

# Generating a Country Select box
To create a simple select box containing all countries, create an empty select element with an ID and a place holder (The place holder will be used as the default option in the select box).

Once you have done that, simply call the countrySelector.countrySelect method passing in the ID of the select box.

```html
<!-- Empty select with an ID and a placeholder -->
<select id="countries" placeholder="Please select a country"></select>

<script>
  	// Onload event is triggered once all content has been loaded.
	window.onload = function () {
		// Populate and link country and region select with the ID of 'countries'
		countrySelector.countrySelect('countries');
	};
</script>
	
// Load the country selector file.
<script src="countries.min.js"></script>
```

**Please note that the countries.js (countries.min.js for production) file must have been included, and the element must be on screen at the time the method is called.

# Generating Country and Region Select Boxes
To create a country select box with a linked region select box you will need to create two empty select boxes with appropriate ID's and placeholders.

Once you have done this you can call the countrySelector.countrySelect method and pass through the ID of the country select box followed by the ID of the region select box.

```html
<!-- Empty select with an ID and a placeholder -->
<select id="countries" placeholder="Please select a country"></select>
<select id="regions" placeholder="Please select a region"></select>

<script>
  	// Onload event is triggered once all content has been loaded.
	window.onload = function () {
		// Populate and link country and region select with the ID of 'countries'
		countrySelector.countrySelect('countries', 'regions');
	};
</script>
	
// Load the country selector file.
<script src="countries.min.js"></script>
```

# Jquery Auto Complete Widget
If you have access to Jquery UI in your application you can use the autocomplete function that it provides to create dropdowns that will try to auto complete for your users as they enter their country or region name.

To generate autocompleting drop downs you will need to create text inputs with appropriate ID's and placeholders then call the countrySelector.autoComplete method passing in the ID of the countries input followed by the ID of regions input.

*Please note that the ID needs to include the '#' symbol for jquery ID lookups at the begining. Eg: '#countries'.

## For an Auto Completing Country Selector
```html
<!-- Empty select with an ID and a placeholder -->
<input id="CountryAutoComplete" placeholder="Please select a country">
<input id="RegionAutoComplete" placeholder="Please select a region">

<script>
  	// Onload event is triggered once all content has been loaded.
	window.onload = function () {
		// Populate and link country and region select with the ID of 'countries'
		countrySelector.autoComplete('#CountryAutoComplete');
	};
</script>
	
// Load the country selector file.
<script src="countries.min.js"></script>
```

## For Auto Completing Country and Region Selectors
```html
<!-- Empty input with an ID and a placeholder -->
<input id="CountryAutoComplete" placeholder="Please select a country">
<input id="RegionAutoComplete" placeholder="Please select a region">

<script>
  	// Onload event is triggered once all content has been loaded.
	window.onload = function () {
		// Populate and link country and region select with the ID of 'countries'
		countrySelector.autoComplete('#CountryAutoComplete', '#RegionAutoComplete');
	};
</script>
	
// Load the country selector file.
<script src="countries.min.js"></script>
```

---

# Country Selector API
The country selector affers a set of utility functions for those looking to write their own implementation. For a full understanding please see the countries.js file where each method can be viewed and edited as needed. 

## countrySelect
Generates a country select box and if required a linked region select box.

**Paramaters **
1. ID of the country select box "countries"
2. ID of the region select box (optional) "regions"

## getRegionsByCountry
Returns all the regions based on a given Country name. Please note that only countries that exist in the countries.js file will be matched.

**paramaters**
1. Name of a country EG: "South Africa"

## getCountries
returns an array of country names

**paramaters**
1. none

## getCountriesAndRegions
Returns a multi dimensional object of country names with nested regions.

**paramaters**
1. none

## populateRegions
Will extract the selected country from the named country select and populate the named region select box with regions for that country.

**Paramaters **
1. ID of the region select box EG:"regions"
2. ID of the country select box EG:"countries"

## autoComplete
Will create auto completing text boxes based on the Jquery UI auto complete widget.

*Note IDs must be prefixed with the '#' symbol.

**Paramaters **
1. ID of the country select box "#countries"
2. ID of the region select box (optional) "#regions"

# Credits

Data provided by http://www.geobytes.com

http://www.geobytes.com/downloads/geoworldmaploader.tar
