# Configuration Cache Lock

This modification for Magento 1.x prevents multiple processes from generating the configuration cache on cold cache, reducing CPU load on frontend web servers.

## Installation

Add the following settings to your local.xml inside the `<global>` node:

		<global>
			...
			<cache_lock>
				<enable>1</enable> <!-- If cache locking is enabled or not -->
				<server>127.0.0.1</server> <!-- The Redis database IP -->
				<port>6379</port> <!-- The Redis port -->
				<database>0</database> <!-- The Redis Database to use -->
				<password></password> <!-- The password of the Redis server -->
				<timeout>2.5</timeout> <!-- The Redis timeout -->
				<key>cache_lock</key> <!-- The name of lock in the Redis Database -->
				<max_attempts>10</max_attempts> <!-- The maximum amount of times to retry the connection. Defaults to 10. -->
				<retry_time>10000000</retry_time> <!-- The amount of microseconds to wait between checking the cache has generated. Defaults to 10000000 -->
			</cache_lock>
		</global>

## Credits

I first heard about this project at [Mage Titans](http://www.magetitans.co.uk/) 2015 during a talk by Paul Partington, the slides can be found [here](http://www.slideshare.net/paupartington/mage-titans-2015).

Thanks to [ctidigital](https://www.ctidigital.com/) for their work on this project.  You can find the original repository [here](https://github.com/ctidigital/Configuration-Cache-Lock).
