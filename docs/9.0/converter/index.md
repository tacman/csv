---
layout: default
title: Records conversion in popular formats
---

# Records conversion

## Converter classes

The package provides classes which convert any collection of CSV records into:

- a `DOMDocument` object using the [XMLConverter](/9.0/converter/xml/) class;
- an HTML table using the [HTMLConverter](/9.0/converter/html/) class;
- an JSON document using the [JsonConverter](/9.0/converter/json/) class;

<p class="message-warning"><strong>Warning:</strong> A <code>League\Csv\Writer</code> object can not be converted.</p>

## Converters are immutable

Before conversion, you may want to configure your converter object. Each provided converter exposes additional methods to correctly convert your records.

When building a converter object, the methods do not need to be called in any particular order, and may be called multiple times. Because all provided converters are immutable, each time their setter methods are called they will return a new object without modifying the current one.

## Converters exceptions

Because converters do not directly deals with CSV document but with their contents. On error these classes trigger PHP's Exceptions instead of `League\Csv\Exception` exception.
