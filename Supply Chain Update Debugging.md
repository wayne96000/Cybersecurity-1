#Room Name - TRY HACK ME
## Objective
Debug security software update has old lib/vulnerable_utils.py. Navigating first to http://10.128.170.15:5003

## Tools used
- Kali Linux
- curl
- JSON

## What i found
lib/vulnerable_utils.py had a backdoor  if data == 'debug':
                                             return jsonify(debug_info())

## How i exploited it
Used curl to send POST request , the debug_info() function dropped the flag, and admin token, an internal secret key and the version
This data is enough for an attacker to take over the system

## What i learned
Dependency scanning in the CI/CD environment is important in scanning every third party library an app imports.
