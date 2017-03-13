# REST API: verwijderen van een miniview

Een miniview kan verwijderd worden door een HTTP DELETE verzoek te sturen naar de volgende URL:

`https://api.copernica.com/v1/miniview/$id?access_token=xxxx`

De $id hier moet vervangen worden door de ID van de selectie die je wilt verwijderen. Let op dat je alleen de miniview verwijderd op deze manieren, alle profielen die het bevat blijven bestaan.

## Voorbeeld in PHP

Het volgende voorbeeld demonstreert hoe je deze methode gebruikt in PHP:

	// vereiste scripts
	require_once('copernica_rest_api.php');

	// verander dit naar je access token
	$api = new CopernicaRestApi("your-access-token");

	// voer het verzoek uit
	$api->delete("miniview/1234");

Dit voorbeeld heeft de [CopernicaRestAPi klasse](rest-php) nodig.

## Meer informatie

* [Overzicht van alle API calls](rest-api)
* [Verwijder een database](rest-delete-database)
* [Vraag miniview regels op](rest-get-miniview)
* [Pas miniview regels aan](rest-put-miniview)
