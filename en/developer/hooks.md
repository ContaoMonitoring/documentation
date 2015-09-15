# Hooks

The following hooks could be used.

**Content**
<!-- toc -->

## "monitoringFormatList" - Hook

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

## "monitoringExtendEntryHeader" - Hook

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

## "monitoringExtendTestResultOutput" - Hook

The "monitoringExtendTestResultOutput" hook is triggered for extending output for a test result in the parent view. So additional fields could be added, or special formatting is possible.
It passes the `$arrRow` (array of data for each row) and the `$arrOutputTable` (the output array containing rows with columns).
It expects the modified output array as return value.

*(since Version 1.7.0)*

```php
// config.php

$GLOBALS['TL_HOOKS']['monitoringExtendTestResultOutput'][] = array('MyMonitoringHookClass', 'myMonitoringExtendTestResultOutput');

// MyMonitoringHookClass.php

class MyMonitoringHookClass
{
	public function myMonitoringExtendTestResultOutput($arrRow, $arrOutputTable)
	{
		// extend the output array here, e.g. $arrOutputTable[] = array('col_0' => 'A label', 'col_1' => 'The content');
		return $arrOutputTable;
	}
}
```