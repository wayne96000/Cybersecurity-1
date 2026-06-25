http://10.128.170.15:5003
trying to debug security software update has old lib/vulnerable_utils.py
lib/vulnerable_utils.py has a backdoor  if data == 'debug':
                                             return jsonify(debug_info())
using curltosendpost request , the debug_info() function droppedd the flag,and admin token, an internalsecret key and the version
this data is enough for an attacker to take over the system
