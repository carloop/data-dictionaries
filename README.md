# data-dictionaries
CAN data dictionaries for cars in production

## List of cars

Add the data dictionary for your car by submitting a pull requets to this repository!

## Data dictionary format

Here's an example data dictionary in JSON.

```json
{
	"fileformat": "carloop-v1",
	"description": "Ford Fiesta Gen 4",
	"vehicles": [{
		"make": "Ford",
		"model": "Fiesta",
		"year": 2011
	}],
	"buses": [{
		"bus": 1,
		"type": "CAN",
		"speed": 500000
	}],
	"messages": [{
		"name": "EngineStatus1",
		"id": "0x100",
		"extended": false,
		"length": 8,
		"nominal_rate": 0.1,
		"signals": [{
			"name": "EngineSpeed",
			"unit": "1/min",
			"description": "Engine speed",
			"start_bit": 8,
			"bit_length": 16,
			"bit_order": "little_endian",
			"factor": 0.01,
			"offset": 0
		}]
	}]
}
```

## Data trace format

Here's a sample format for recording CAN data. First line is optional and contains information about the event being analyzed. Each other line is a JSON object with a UNIX timestamp, the bus number (for vehicles with more than 1 CAN bus) and the data in hex.

```JSON
{"metadata": { "vehicle": { "make": "Ford", "model": "Fiesta", "year": 2011 }, "description": "Drive home" }
{"timestamp": 1465332213.3144, "bus": 1, "id": "0x100", "data": "0x1234567812345678"}
{"timestamp": 1465332213.3244, "bus": 1, "id": "0x100", "data": "0x5534567812345678"}
{"timestamp": 1465332213.3344, "bus": 1, "id": "0x100", "data": "0x6634567812345678"}
{"timestamp": 1465332213.3444, "bus": 1, "id": "0x100", "data": "0x7734567812345678"}
```

## License

These data format is available under the Creative Commons Public Domain Dedication (CC0) license.

Inspired by [the OpenXC message format.](https://github.com/openxc/openxc-message-format)
