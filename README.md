# pyzipcode3

This package will allow you to get zip code information using the Maxmind Cities DB. 
Initially a fork of [https://bitbucket.org/vangheem/pyzipcode](https://bitbucket.org/vangheem/pyzipcode) but has been updated to support Python 3.

*pyzipcode* uses a local sqlite database. You can replace it with your own other storage mechanism with a little effort.

## Installation

    pip install pyzipcode3

## Usage

#### Simple Lookup

	>>> from pyzipcode import ZipCodeDatabase
	>>> zcdb = ZipCodeDatabase()
	>>> zipcode = zcdb[10013]
	>>> zipcode.zip
	u'10013'
	>>> zipcode.place
	u'New York'
	>>> zipcode.state
	u'NY'
	>>> zipcode.longitude
	-74.00526
	>>> zipcode.latitude
	40.720666
	>>> zipcode.timezone
	-5
	
	
#### Search for ZIPs

	>>> from pyzipcode import ZipCodeDatabase
	>>> zcdb = ZipCodeDatabase()
	>>> len(zcdb.find_zip(place="Oshkosh"))
	7
	

#### Get ZIPs around a given ZIP
	
	>>> from pyzipcode import ZipCodeDatabase
	>>> zcdb = ZipCodeDatabase()
	>>> [z.zip for z in zcdb.get_zipcodes_around_radius('54901', 10)]
	[u'54901', u'54902', u'54903', u'54904', u'54906', u'54927', u'54952', u'54956', u'54957', u'54979', u'54985']