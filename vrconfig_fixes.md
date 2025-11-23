# Here are fixes to vrconfig to correct finding the first pilot seat.

## For `Airbus A330-300`:

`BEGIN_TELEPORT_HOTSPOT` should be the following for the plugin to find the right position of the first pilot seat:
```
BEGIN_TELEPORT_HOTSPOT SITTING Pilot's Seat
	AABB -1.0 -0.8 1.0 0.0 1.50 2.65
	PRESET_XYZ -0.47079298 2.027514 -26.562862
	PRESET_PSI 0.0
	PRESET_THE 0.0
	PRESET_PHI 0.0
END_TELEPORT_HOTSPOT
```

The original position seems to be wrong.
