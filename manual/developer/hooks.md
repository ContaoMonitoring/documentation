# Hooks

The following hooks could be used.

## monitoringFormatList

The "monitoringFormatList" hook is triggered for formatting the monitoring list. So custom formats or icons are possible for each column.
It passes the `$arrRow` (array of data for each row), the `$dc` (the DataContainer object) and the `$arrFormatedColumns` (array of already formatted columns).
It expects the modified array of columns as return value.

*(since Version 1.5.0)*

```php
// config.php

$GLOBALS['TL_HOOKS']['monitoringFormatList'][] = array('MyMonitoringHookClass', 'myMonitoringFormatList');

// MyMonitoringHookClass.php

class MyMonitoringHookClass
{
	public function myMonitoringFormatList($arrRow, DataContainer $dc, $arrFormatedColumns)
	{
		// format columns here
		return $arrFormatedColumns;
	}
}
```

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