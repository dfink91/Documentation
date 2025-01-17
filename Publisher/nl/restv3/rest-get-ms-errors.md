# REST API: GET errors (Marketing Suite)

Er worden statistieken bijgehouden over elke mailing die verstuurd wordt met 
Copernica om je meer inzicht te geven in de prestatie hiervan. Errors zijn 
een van de statistieken die worden bijgehouden. 
Je kan alle errors voor een account opvragen met een HTTP GET call naar de volgende URL:

`https://api.copernica.com/v3/ms/errors?access_token=xxxx`

## Parameters

De parameters voor deze methode kunnen ingesteld worden om alleen de 
statistieken voor een bepaalde periode op te halen. De volgende optionele 
parameters zijn beschikbaar:

* **begintime**: De tijdstempel waarna de error gemeld moet zijn (YYYY-MM-DD HH:MM:SS format).
* **endtime**: De tijdstempel waarvoor de error gemeld moet zijn (YYYY-MM-DD HH:MM:SS format).

## Teruggegeven velden

Deze methode geeft een JSON object terug met errors onder het 'data' veld. 
Voor elke error is de volgende informatie beschikbaar:

* **ID**: The ID van de error.
* **mailing**: The ID van de mailing.
* **timestamp**: Tijdstempel van de error.
* **status**: De status van de error.
* **errorcode**: De code geassocieerd met deze error.
* **description**: Beschrijving van de error.
* **errortype**: Het type error dat herkend is.
* **destination**: De ID van de destination die de error veroorzaakte.
* **profile**: De ID van het profiel die de error veroorzaakte.
* **subprofile**: De ID van het subprofiel die de error veroorzaakte.

### JSON voorbeeld

Een enkele error ziet er bijvoorbeeld zo uit:

```json
{  
   "ID":"2",
   "mailing":"234",
   "timestamp":"2015-03-09 15:36:39",
   "status":null,
   "errorcode":"0",
   "description":"No valid from address is set",
   "errortype":"",
   "destination":"764416",
   "profile":null,
   "subprofile":null
}
```

## PHP voorbeeld

Dit script demonstreert hoe je de API methode kunt gebruiken:

```php
// vereiste scripts
require_once('copernica_rest_api.php');

// verander dit naar je access token 
$api = new CopernicaRestAPI("your-access-token", 3);

// voer het verzoek uit
print_r($api->get("ms/errors"));
```

Dit voorbeeld vereist de [REST API klasse](./rest-php).

## Meer informatie

* [Overzicht van alle REST API calls](./rest-api)
* [Opvragen van abuses voor MS](./rest-get-ms-abuses)
* [Opvragen van clicks voor MS](./rest-get-ms-clicks)
* [Opvragen van deliveries voor MS](./rest-get-ms-deliveries)
* [Opvragen van impressions voor MS](./rest-get-ms-impressions)
* [Opvragen van unsubscribes voor MS](./-rest-get-ms-unsubscribes)
