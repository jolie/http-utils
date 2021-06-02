# Jolie HTTP utils

A utility library for HTTP.

## Installation

`jpm add @jolie/http-utils`

## Usage example

```jolie
from @jolie.http-utils import HttpUtils

service Example {
	embed HttpUtils as httpUtils

	main {
		// Connect to the stream
		connectStream@httpUtils( {
			uri = "https://your-website"
		} )( sid )

		provide
			[ next( mesg ) ] {
				// Received a message in the stream
			}
		until
			[ end( m ) ] {
				// Stream ended
			}
	}
}
```