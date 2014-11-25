# Hooks

The following hooks could be used.

## monitoringExtendEntryHeader

The "monitoringExtendEntryHeader" hook is triggered for extending the header in the parent view of each test entry. So custom fields could be added, or special formatting is possible.
It passes the `$arrHeaderFields` (array of header fields) and the `$dc` (the DataContainer object).
It expects the modified array of header fields as return value.

*(since Version 1.4.0)*

```php
// config.php

$GLOBALS['TL_HOOKS']['monitoringExtendEntryHeader'][] = array('MyMonitoringHookClass', 'myMonitoringExtendEntryHeader');

// MyMonitoringHookClass.php

class MyMonitoringHookClass
{
	public function myMonitoringExtendEntryHeader($arrHeaderFields, DataContainer $dc)
	{
		// extend header here
		return $arrHeaderFields;
	}
}
```