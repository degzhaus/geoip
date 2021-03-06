# GeoIP API for Go

This package wraps the [libgeoip C library](http://www.maxmind.com/app/c) for
access from Go (golang).

Install with `go get https://github.com/abh/geoip` and use `godoc
geoip` to read the documentation.

There's a small example in the `ex/` subdirectory.

You can download the free [GeoLite
Country](http://www.maxmind.com/app/geoip_country) database or you can
[subscribe to updates](http://www.maxmind.com/app/country).

## Examples

	file := "/usr/share/GeoIP/GeoIP.dat"

	gi := geoip.Open(file)
	if gi == nil {
		fmt.Printf("Could not open GeoIP database\n")
	}

	if gi != nil {
		country := gi.GetCountry("207.171.7.51")
	}

	// Setup gi6 by opening the optional IPv6 database and then:	
	country := gi6.GetCountry_v6("2607:f238:2::5")
	display(country)


## Contact

Ask Bjørn Hansen <ask@develooper.com>. The package MIT licensed, see the
LICENSE file. Originally based on an example from blasux@blasux.ru.