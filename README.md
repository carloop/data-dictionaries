# data-dictionaries
CAN data dictionaries for cars in production

## List of cars

Add the data dictionary for your car by submitting a pull requets to this repository!

## Data format

Here's an example data dictionary in JSON.

```json
{
  "description": "Ford Fiesta Gen 4",
  "vehicles": [
    {
      "manufacturer": "Ford",
      "model": "Fiesta",
      "model_year": 2011
    }
  ],
  "messages": [
    "id": "0x100",
    "extended": false,
    "length": 8,
    "signals": [
      {
        "name": "EngineSpeed",
        "unit": "1/min",
        "description": "Engine speed",
        "start_bit": 8,
        "length": 16,
        "bit_order": "little_endian",
        "slope": 0.01,
        "offset": 0
      }
    ]
  ]
}
```
