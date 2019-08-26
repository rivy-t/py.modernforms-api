# Modern Forms smart fan interface
[Modern Forms](http://moderforms.com/fan/) has a collection of cloud connected Wi-Fi smart fans.  They can be controlled via their app, but they also support local control.  This project is an interface to control their fans locally via the REST API on the fan.

All aspects of the fan and option light kit can be controlled.

## Invocation
Import into your code and create a `ModernFormsFan` object

```python
from modernforms import moderforms_fan
fan = moderforms_fan.ModerFormsFan('192.168.1.10', 5)
```
Constructor take 2 arguments.  The IP or hostnane (if you DNS registered your fan) and the timeout for communicating with the fan.

The timeout is optional and has a default value of 5.

### Fan Control
The fan has 3 attributes to control:
* fan_on
* fan_speed
* fan_direction
```python
>>> fan.fan_on
False
>>> fan.fan_on = True
>>> fan,fan_on 
True
```

### Light Control
The light kit has two attributes to control:
* light_on
* light_brightness
```python
>>> fan.light_on
False
>>> fan.lingt_on = True
>>> fan,light_on 
True
```

**This interface does not perform any error handling.  No `exception` are caught so they can be passed up the calling stack and handled in code that implements this interface.**  You should consider wrapping your calls to this interface in `try` `catch` blocks.