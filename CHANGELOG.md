# Changelog

All Notable changes to `Csv` will be documented in this file

## [9.24.1](https://github.com/thephpleague/csv/compare/9.24.0...9.24.1) - 2025-06-25

### Added

- None

### Deprecated

- None

### Fixed

- Fix possible memory leaks with the `Writer` class [#563](https://github.com/thephpleague/csv/issues/563) - thanks to [pope-12](https://github.com/pope-12)

### Remove

- None

## [9.24.0](https://github.com/thephpleague/csv/compare/9.23.0...9.24.0) - 2025-06-24

### Added

- `TabularData::last` and `TabularData::lastAsObject`

### Deprecated

- None

### Fixed

- Improved implementation for `AbstractCsv::download` method

### Remove

- None

## [9.23.0](https://github.com/thephpleague/csv/compare/9.22.0...9.23.0) - 2025-03-28

### Added

- `TypeCastingInfo` to improve the error message when type casting fails during denormalization [#561](https://github.com/thephpleague/csv/pull/561)

### Deprecated

- `fetchColumnByOffset` and `fetchColumnByName` use `fetchColumn` instead.

### Fixed

- Test suite around header testing using Xdebug functions [#559](https://github.com/thephpleague/csv/pull/559)

### Remove

- None

## [9.22.0](https://github.com/thephpleague/csv/compare/9.21.0...9.22.0) - 2025-02-28

### Added

- `Writer::necessaryEnclosure`
- `TabularDataReader::selectAllExcept`
- `Statement::selectAllExcept`
- `ResultSet::from` and `ResultSet::tryFrom`
- `RdbmsResult` class to ease importing RDBMS result into the package classes
- `TabularData` interface
- `Buffer` class
- `XMLConverter::supportsHeader`
- `XMLConverter::when`
- `HTMLConverter::when`
- `JsonConverter::when`
- `CharsetConverter::appendOnReadTo`, `CharsetConverter::appendOnWriteTo`, `CharsetConverter::prependOnReadTo`, `CharsetConverter::prependOnWriteTo`

### Deprecated

- `Writer::relaxEnclosure` use `Writer::necessaryEnclosure`
- `ResultSet::createFromTabularDataReader` use `ResultSet::from`
- `ResultSet::createFromRecords` use `ResultSet::from`
- `ResultSet::__construct` is marked as being `internal` and deprecated before being made private use `ResultSet::from`
- `XMLConverter::convert` use `XMLConverter::import` instead
- `XMLConverter::create` use `XMLConverter::__construct` instead
- `HTMLConverter::create` use `HTMLConverter::__construct` instead
- `Statement::create` use `Statement::__construct` instead
- `FragmentFinder::create` use `FragmentFinder::__construct` instead
- `CharsetConverter::appendTo`, `CharsetConverter::prependTo` use the more strict methods added on the instance

### Fixed

- `Comparison::CONTAINS` must check the value is a string before calling `str_compare` [#548](https://github.com/thephpleague/csv/pull/548) by [cage-is](https://github.com/cage-is)
- Fix testing to improve Debian integration [#549](https://github.com/thephpleague/csv/pull/549) by [David Prévot and tenzap](https://github.com/tenzap)
- `Bom::tryFromSequence` and `Bom::fromSequence` supports the `Reader` and `Writer` classes.
- `XMLConverter::$formatter` should not be public.
- `XMLConverter` internal rewritten to take advantage of PHP8.4 new dom classes
- `HTMLConverter` internal rewritten to take advantage of PHP8.4 new dom classes
- `XMLConverter::fieldElement` now has a `nullable` field element to allow using headers names as cell names.

### Removed

- None

## [9.21.0](https://github.com/thephpleague/csv/compare/9.20.1...9.21.0) - 2025-01-08

### Added

- `TabularDataReader::map` method.
- `StreamFilter` class
- `CallbackStreamFilter` class
- `AbstractCsv::appendStreamFilterOnRead`
- `AbstractCsv::appendStreamFilterOnWrite`
- `AbstractCsv::prependStreamFilterOnRead`
- `AbstractCsv::prependStreamFilterOnWrite`
- `Stream::getMode` returns the underlying stream mode; internal codebase.

### Deprecated

- `AbstractCsv::addStreamFilter` use `AbstractCsv::appendStreamFilterOnRead` or `AbstractCsv::appendStreamFilterOnWrite` instead.

### Fixed

- Improve `CharsetConverter` and `SwapDelimiter` internal code.
- Fix `supportStreamFilterOnRead`and `supportStreamFilterOnWrite` to expose the document real stream filter capabilities.

### Removed

- None

## [9.20.1](https://github.com/thephpleague/csv/compare/9.20.0...9.20.1) - 2024-12-18

### Added

- None

### Deprecated

- None

### Fixed

- [#554](https://github.com/thephpleague/csv/pull/544) Fix stream filte removal by [crocodele](https://github.com/crocodele)
- Fix Statement callback and closure signature

### Removed

- None

## [9.20.0](https://github.com/thephpleague/csv/compare/9.19.0...9.20.0) - 2024-12-13

### Added

- `XMLConverter::formatter`
- `HTMLConverter::formatter`
- `Writer::encloseNone`
- `Writer::encloseNecessary`
- `Writer::noEnclosure`

### Deprecated

- None

### Fixed

- `JsonConverter::formatter` now accepts callable before only `Closure` where accepted.
- The protected property `Writer::$enclose_all` is no longer a boolean but an integer

### Removed

- None

## [9.19.0](https://github.com/thephpleague/csv/compare/9.18.0...9.19.0) - 2024-12-08

### Added

- `JsonConverter::withPrettyPrint` now accepts an optional `$identSize` parameter as its unique parameter.
- `Statement::when` to enable conditionable query building.
- Using PHP8.4 `Deprecated` attribute to signal deprecated public API methods and constants.

### Deprecated

- `JsonConverter::indentSize`

### Fixed

- Adding forgotten support for `callable` in the `Query\Constraint` namespace.
- Fix `HttpHeaders::forFileDownload` to be inline with RFC2183 and HTTP field name and value best practices.

### Remove

- None

## [9.18.0](https://github.com/thephpleague/csv/compare/9.17.0...9.18.0) - 2024-10-18

### Added

- `League\Csv\JsonConverter::chunkSize`
- `League\Csv\AbstractCsv::download`

### Deprecated

- `League\Csv\AbstractCsv::output` use `League\Csv\AbstractCsv::download` instead
- `League\Csv\FragmentFinder` and derived methods are marked as **experimental** as their results will be changed in the next major version.

### Fixed

- `League\Csv\JsonConverter::download` the filename is now nullable
- `League\Csv\XMLConverter::download` the filename is now nullable
- `League\Csv\JsonConverter::save` throws a `TypeError` exception if the `$destination` type is not supported.

### Remove

- None

## [9.17.0](https://github.com/thephpleague/csv/compare/9.16.0...9.17.0) - 2024-10-10

### Added

- `League\Csv\SwapDelimiter::apppendTo`
- `League\Csv\SwapDelimiter::prependTo`
- `League\Csv\CharsetConverter::apppendTo`
- `League\Csv\CharsetConverter::prependTo`
- `League\Csv\XMLConverter::download`
- `League\Csv\JsonConverter`
- `League\Csv\Constraint\Criteria::andNot`
- `League\Csv\Constraint\Criteria::orNot`
- `League\Csv\Constraint\Criteria::xorNot`
- `League\Csv\Serializer\MapRecord` attribute
- adding the `convertEmptyStringToNull` options to `MapCell` and to `MapRecord` to improve string and `null` conversion
- adding the `trimFieldValueBeforeCasting` options to `MapCell` and to `MapRecord` to improve string conversion
- adding the `trimElementValueBeforeCasting` option to `CasToArray` to improve conversion during denormalization
- adding the `headerOffset` option to `CasToArray` to improve conversion during denormalization. The optoon is only used with the CSV shape.

### Deprecated

- None

### Fixed

- `Cast*` methods accept more input type to improve Denormalization usage when `Reader::addFormatter` is used or when the collection contains data other than string and `null`.
- `Stream::getSize` is added to the internal `Stream` class
- `Stream::getContents` is added to the internal `Stream` class
- `MapIterator::toIterator` is added to the internal class `MapIterator` class to convert any `iterable` into an `Iterator`.
- Casting a CSV to an `array` it now will be a collection of array instead of a simple `array`.
- Added the internal class `HttpHeaders` to improve file download throughout the codebase.

### Removed

- `leage\csv-doctrine` is no longer a sub-split of the main `league/csv` package.

## [9.16.0](https://github.com/thephpleague/csv/compare/9.15.0...9.16.0) - 2024-05-24

### Added

- `Bom` enum
- `Stream::ftell`
- `Statement::orderByAsc`
- `Statement::orderByDesc`
- `Statement::andWhere`
- `Statement::whereNot`
- `Statement::orWhere`
- `Statement::xorWhere`
- `Statement::andWhereColumn`
- `Statement::whereNotColumn`
- `Statement::orWhereColumn`
- `Statement::xorWhereColumn`
- `Statement::andWhereOffset`
- `Statement::whereNotOffset`
- `Statement::orWhereOffset`
- `Statement::xorWhereOffset`
- `Query` feature to allow easier filtering, ordering and querying tabular data

### Deprecated

- `ByteSequence` Interface use the `Bom` enum instead
- `Info::fetchBOMSequence` use `Bom::tryFromSequence` instead
- `League\Csv\Doctrine` use the new `League\Csv\Constraint` feature instead
- `League\Csv\Statement::create` arguments; The method should be used without any argument at all. All arguments will be removed in the next major version.

### Fixed

- `Reader` and `ResultSet` docblocks
- internal code uses `Bom` enum instead of `Info::fetchBOMSequence`
- the `AbstractCsv` BOM related properties are moved to being `Bom` instances instead of nullable string.
- `setOutpuBOM` will only accept valid BOM sequences all other values except the empty string will throw a `ValueError` exception;
- The package no longer requires the `ext-mbstring` extension to work. But you should have it install in your system in order to use the `mbstring` related stream filters.
- Issue [#524](https://github.com/thephpleague/csv/issues/524) fix issue with `ResultSet::chunkBy` not working as documented.

### Removed

- None

## [9.15.0](https://github.com/thephpleague/csv/compare/9.14.0...9.15.0) - 2023-02-20

### Added

- `Statement::select`
- `TabularDataReader::getRecordsAsObject`
- `TabularDataReader::chunkBy`
- `TabularDataReader::mapHeader`

### Deprecated

- `TabularDataReader::getObjects` use `TabularDataReader::getRecordsAsObject` instead

### Fixed

- `Reader::select` and `ResultSet::select` now internally use `Statement::select`
- `Statement` should not throw when `LimitIterator` is used in combinaison with `ArrayIterator`.
- `Statement` internal codebase improvement.
- Using the `$header` argument on `Statement::process` is no longer deprecated. `E_USER_DEPRECATED` is no longer triggered.
- BOM stripping no longer depends on the `mbstring` extension
- `TabularDataReader::fetchColumn` is no longer deprecated

### Removed

- None

## [9.14.0](https://github.com/thephpleague/csv/compare/9.13.0...9.14.0) - 2023-12-29

### Added

- `League\Csv\TabularDataReader::nthAsObject` equivalent to `nth` but returns an object or `null`
- `League\Csv\TabularDataReader::firstAsObject` equivalent to `first` but returns an object or null
- `League\Csv\Serializer\Denormalizer::types` list all the registered types

### Deprecated

- None

### Fixed

- None

### Removed

- None

## [9.13.0](https://github.com/thephpleague/csv/compare/9.12.0...9.13.0) - 2023-12-16

### Added

- `League\Csv\SwapDelimiter` stream filter to allow working with multibyte CSV delimiter
- `League\Csv\Serializer\AfterMapping` to work around the limitation of not using the class constructor during denormalization.
- `League\Csv\Serializer\Denormalizer` to allow registering type alias to improve callback usage.
- `League\Csv\Serializer\MapCell` has a new property `ignore` to allow ignoring a property or a method during denormalization.

### Deprecated

- None

### Fixed

- None

### Removed

- None

## [9.12.0](https://github.com/thephpleague/csv/compare/9.11.0...9.12.0) - 2023-12-02

### Added

- `TabulatDataReader::value`
- `TabulatDataReader::select`
- `TabulatDataReader::getObjects`
- `TabulatDataReader::matching`
- `TabulatDataReader::matchingFirst` 
- `TabulatDataReader::matchingFirstOrFail`
- `ResultSet::fromRecords`
- `Stream::setMaxLineLen`
- `Stream::getMaxLineLen`
- `League\Csv\Serializer\Denormalizer` to allow denormalizing records into objects [#508](https://github.com/thephpleague/csv/issues/508)
- `League\Csv\FragmentFinder` to implement [RFC7111](https://www.rfc-editor.org/rfc/rfc7111)

### Deprecated

- Using the `$header` argument on `Statement::process` is deprecated and will be removed in
the next version. Use `TabularDataReader::getRecords` on the returned value instead.
It's usage will trigger a `E_USER_DEPRECATED` call.

### Fixed

- The optional `$header` argument for `TabularDataReader::getRecords` becomes a full mapper between the records column offset and the column names [#498](https://github.com/thephpleague/csv/issues/498)
- `ResultSet` constructor now allows the records to be an `array`.
- The internal `Stream` object will throw a `RuntimeException` if the rewind action fails
- if calls to `fseek` fails (returns `-1` ) a `RuntimeException` will be thrown.
- `Stream` can iterate and return the full line respecting `SplFielObject` flags. Previously it only returned the CSV records.
- `MapIterator::fromIterable` to instantiate a `MapIterator` object from any iterable structure.

### Removed

- None

## [9.11.0](https://github.com/thephpleague/csv/compare/9.10.0...9.11.0) - 2023-09-23

### Added

- `EscapeFormula::unescapeRecord` does the opposite of `EscapeFormula::escapeRecord`
- `TabularReader::each` (implemented on the `Reader` and the `ResultSet` object)
- `TabularReader::exists` (implemented on the `Reader` and the `ResultSet` object)
- `TabularReader::reduce`  (implemented on the `Reader` and the `ResultSet` object)
- `TabularReader::filter` (implemented on the `Reader` and the `ResultSet` object)
- `TabularReader::slice` (implemented on the `Reader` and the `ResultSet` object)
- `TabularReader::sorted` (implemented on the `Reader` and the `ResultSet` object)
- `Reader::addFormatter` (implemented on the `Reader` and the `ResultSet` object)

### Deprecated

- `EscapeFormula::__invoke` use `EscapeFormula::escapeRecord` instead

### Fixed

- None

### Removed

- None

## [9.10.0] - 2023-08-04

### Added

- `Writer::forceEnclosure` and `Writer::relaxEnclosure` to control the presence of enclosure in the generated CSV
- `Writer::getEndOfLine` and `Writer::setEndOfLine` 

### Deprecated

- `EncloseField` stream filter in favor of the new `Writer::forceEnclosure` method.
- `Writer::getNewline` and `Writer::setNewline` in favor of `Writer::getEndOfLine` and `Writer::setEndOfLine`

### Fixed

- `Stream::fwrite` to allow writing to a file in a normalized way. Internal use.
- Documentation Fixed removing unreleased documented feature by [@nclavaud](https://github.com/nclavaud)

### Removed

- None

## [9.9.0] - 2023-03-11

### Added

- `TabularDataWriter` interface to represent how to write to a tabular data document.
- `TabularDataReader::first` to replace `TabularDataReader::fetchOne`
- `TabularDataReader::nth` to replace `TabularDataReader::fetchOne`
- `CharsetConverter::addBOMSkippingTo` to improve BOM skipping see [bug #483](https://github.com/thephpleague/csv/issues/483)

### Deprecated

- `TabularDataReader::fetchOne`

### Fixed

- `Stream::createFromResource`
- `Stream::__construct` is made private. The class is already marked as internal so BC break does not apply on it.

- Using PHP8 feature to rewrite internal codebase
- Replaced simple comparisons with strict comparison operator where types are obvious in internal codebase by [@astepin](https://github.com/astepin)
- Marked class constants explicitly as public by [@astepin](https://github.com/astepin)
- Minimal support version PHP8.1.2
- Fix Docblock and method signature using PHP8 feature (Union Type)
- Fix Internal codebase around `seek` usage and `[#75917](https://bugs.php.net/bug.php?id=75917) requires PHP8.1.2
- Remove internal usage of deprecated methods

### Removed

- `Stream::fwrite` The class is already marked as internal so BC break does not apply on it.
- `Stream::fgets` The class is already marked as internal so BC break does not apply on it.
- Drop support for PHP7 and PHP8.0
- Polyfill to enable using fputcsv `$eol` argument

## [9.8.0] - 2022-01-04

### Added

- Added PHP7.4 typed properties where applicable
- `TabularDataReader::fetchColumnByName` to replace `TabularDataReader::fetchColumn`
- `TabularDataReader::fetchColumnByOffset` to replace `TabularDataReader::fetchColumn`

### Deprecated

- `TabularDataReader::fetchColumn` use `TabularDataReader::fetchColumnByOffset` or `TabularDataReader::fetchColumnByName` instead

### Fixed

- `AbstractCsv` constructor is marked final via docblock.  
 The method should never be extended or changed in child classes to avoid unexpected behaviour

### Removed

- PHP7.3 support
- Remove internal `EmptyEscapeParser` Polyfill used in `Reader` class
- Remove PHP7.4 polyfill features in `Writer` class

## [9.7.4] - 2021-11-30

### Added

- None

### Deprecated

- None

### Fixed

- Bug fix `EscapeFormula` to follow OWASP latest recommendation [PR #452](https://github.com/thephpleague/csv/pull/452)  
thanks to [@robertfausk](https://github.com/robertfausk) and [@Lehmub](https://github.com/Lehmhub)

### Removed

- None

## [9.7.3] - 2021-11-21

### Added

- None

### Deprecated

- None

### Fixed

- Update PHPStan requirement for development
- Improve Documentation generation thanks to [pdelre](https://github.com/pdelre)
- PHP8.1 compliance: using `ReturnTypeWillChange` to avoid emitting a unnecessary deprecation notice. thanks to [cedric-anne](https://github.com/cedric-anne)

### Removed

- None

## [9.7.2] - 2021-10-05

### Added

- None

### Deprecated

- None

### Fixed

- Update dependencies requirement for development
- PHP8.1 compliance: replace `FILTER_SANITIZE_STRING` by `FILTER_UNSAFE_RAW`
- PHP8.1 compliance: remove duplicated public properties declaration
- PHP8.1 compliance: add support for fputcsv `$eol` argument

### Removed

- None

## [9.7.1] - 2021-04-17

### Added

- None

### Deprecated

- None

### Fixed

- fix writer filter [#421](https://github.com/thephpleague/csv/pull/421) by [LosingBattle](https://github.com/cpj555)

### Removed

- None

## [9.7.0] - 2021-03-26

### Added

- `League\Csv\SyntaxError::duplicateColumnNames` to expose column name duplicates during header usage
- `League\Csv\UnableToProcessCsv` as the new Exception Marker Interface
- `League\Csv\UnavailableStream` as the new Exception
- `League\Csv\Info::getDelimiterStats` to replace the namespace function `delimiter_detect`
- `League\Csv\Info::fetchBOMSequence` to replace the namespace function `bom_match`
- `League\Csv\AbstractCsv::toString` to replace `League\Csv\AbstractCsv::getContent` and `League\Csv\AbstractCsv::__toString`
- `League\Csv\XMLConverter::create` to replace `League\Csv\XMLConverter::__construct`
- `League\Csv\HTMLConverter::create` to replace `League\Csv\HTMLConverter::__construct`
- `League\Csv\AbstractCsv::supportsStreamFilterOnRead` and `League\Csv\AbstractCsv::supportsStreamFilterOnWrite` to replace `League\Csv\AbstractCsv::supportsStreamFilter` and `League\Csv\AbstractCsv::getStreamFilterMode`

### Deprecated

- `League\Csv\delimiter_detect` use `League\Csv\Info::getDelimiterStats`
- `League\Csv\bom_match` use `League\Csv\Info::fetchBOMSequence`
- `League\Csv\AbstractCsv::getContent` use `League\Csv\AbstractCsv::toString`
- `League\Csv\AbstractCsv::getStreamFilterMode` use `League\Csv\AbstractCsv::supportsStreamFilterOnRead` or `League\Csv\AbstractCsv::supportsStreamFilterOnWrite`
- `League\Csv\AbstractCsv::supportsStreamFilter` use `League\Csv\AbstractCsv::supportsStreamFilterOnRead` or `League\Csv\AbstractCsv::supportsStreamFilterOnWrite`
- Calling exceptions constructor, use named constructors instead.
- `League\Csv\XMLConverter::__construct` use `League\Csv\XMLConverter::create`
- `League\Csv\HTMLConverter::__construct` use `League\Csv\HTMLConverter::create`

### Fixed

- Move tests into the `src` directory
- Fixed encoder method resolver implementation
- all classes marked as `@internal` are now final
- `League\Csv\AbstractCsv::STREAM_FILTER_MODE` constant replaces `League\Csv\AbstractCsv::$stream_filter_mode`

### Removed

- PHP7.2 support
- `League\Csv\AbstractCsv::$stream_filter_mode`

## [9.6.2] - 2020-12-10

### Added

- Using Github actions as development tools.

### Deprecated

- None

### Fixed

- Adding official support for PHP8 [#405](https://github.com/thephpleague/csv/pull/405) and [#406](https://github.com/thephpleague/csv/pull/406) by [Ion Bazan](https://github.com/IonBazan)

### Removed

- Removing Travis and Scrutinizr as development tools

## [9.6.1] - 2020-09-05

### Added

- None

### Deprecated

- None

### Fixed

- BOM sequence processing fix [#394](https://github.com/thephpleague/csv/issues/394)

### Removed

- None

## [9.6.0] - 2020-03-17

### Added

- More return types and type parameters as supported in PHP7.2+
- `League\Csv\Statement::create` named constructor to ease constraint builder instantiation
- `League\Csv\Statement` can now also process `League\Csv\ResultSet` instances.
- `League\Csv\TabularDataReader` interface to represent how to read tabular data
- `League\Csv\ResultSet::getRecords` has an optional `$header` second argument to make the method works like `League\Csv\Reader::getRecords`
- `League\Csv\ResultSet::createFromTabularDataReader` create a new instance from `League\Csv\TabularDataReader` implementing class.

### Deprecated

- Nothing

### Fixed

- `League\Csv\Reader` no longer uses `__call` to implement `fetchOne`, `fetchPairs` and `fetchColumn` methods.

### Removed

- Internal polyfill for `is_iterable`
- Internal polyfill for `is_nullable_int`
- Support for PHP7.0 and PHP7.1

## [9.5.0] - 2019-12-15

### Added

- Improve package exception throwing by adding new exceptions classes that extends
the `League\Csv\Exception` exception marker class [#360](https://github.com/thephpleague/csv/issues/360), [#361](https://github.com/thephpleague/csv/issues/360)
feature proposed and developed by [Darren Miller](https://github.com/dmlogic)
  - `League\Csv\UnavailableFeature`
  - `League\Csv\InvalidArgument`
  - `League\Csv\SyntaxError`

### Deprecated

- Nothing

### Fixed

- bug fix `bom_match` function see issue [#363](https://github.com/thephpleague/csv/issues/363) resolved based on PR from [Jerry Martinez](https://github.com/jmwebservices)
- bug fix `delemiter_detect` function see issue [#366](https://github.com/thephpleague/csv/issues/366)

### Removed

- Nothing

## [9.4.1] - 2019-10-17

### Added

- Nothing

### Deprecated

- Nothing

### Fixed

- bug fix the escape mechanism polyfill  [#358](https://github.com/thephpleague/csv/pull/358) fix provided by [on2](https://github.com/on2)

### Removed

- Nothing

## [9.4.0] - 2019-10-02

### Added

- Adding support for controlling empty record presence in `Reader::getRecords` return value.
  - `Reader::includeEmptyRecords`
  - `Reader::skipEmptyRecords`
  - `Reader::isEmptyRecordsIncluded`

- Adding support for controlling Input BOM usage in the library:
  - `AbstractCsv::skipInputBOM`
  - `AbstractCsv::includeInputBOM`
  - `AbstractCsv::isInputBOMIncluded`

### Deprecated

- Nothing

### Fixed

- `EmptyEscapeParser::parse` no longer auto skip empty records

### Removed

- Nothing

## [9.3.0] - 2019-07-30

### Added

- `XMLConverter::import` see [#348](https://github.com/thephpleague/csv/pull/348) thanks [@kusabi](https://github.com/kusabi)
- Support for `thead`, `tfoot` and `tbody` in `HTMLConverter::convert` via the addition of
protected methods `HTMLConverter::addHTMLAttributes` and `HTMLConverter::appendHeaderSection` [#348](https://github.com/thephpleague/csv/pull/348) thanks [@kusabi](https://github.com/kusabi)

### Deprecated

- Nothing

### Fixed

- Internal improvement in `Reader` dockblock thanks [@ghobaty](https://github.com/ghobaty).
- Improve strict comparison when using `preg_match`.
- Improve CSV control in `Stream`.

### Removed

- Nothing

## [9.2.1] - 2019-06-08

### Added

- Nothing

### Deprecated

- Nothing

### Fixed

- `AbstractCSV::chunk` see [#325](https://github.com/thephpleague/csv/pull/325) remove CSV flags from the Stream class to avoid infinite loop.
- Internal improve `HTMLConverter`.

### Removed

- Nothing

## [9.2.0] - 2019-03-08

### Added

- Supports for PHP7.4 empty string for the escape character
- Supports for empty string for the escape character with a polyfill for PHP7.4- versions.
- `AbstractCSV::getPathname` see [#321](https://github.com/thephpleague/csv/pull/321) thanks [@tomkyle](https://github.com/tomkyle)

### Deprecated

- `League\Csv\RFC4180Field` use `AbstractCSV::setEscape` method with an empty string instead.

### Fixed

- `AbstractCSV::__construct` correctly initializes properties
- `AbstractCSV::createFromString` named constructor default argument is now an empty string
- `AbstractCSV::setEscape` now accepts an empty string like `fputcsv` and `fgetcsv`
- `Writer::insertOne` fixes throwing exception when record can not be inserted
- `XMLConverter` convert to string the record value to avoid PHP warning on `null` value
- Internal `Stream::createFromString` named constructor default argument is now an empty string
- Internal `Stream::fwrite` improved
- Internal `Stream::__destruct` no longer emit warning on invalid stream filter removal.
- Internal `Stream::seek` returns `0` if the seeked position `0` is valid see [#321](https://github.com/thephpleague/csv/pull/332) thanks [@HaozhouChen](https://github.com/HaozhouChen)

- `Reader:getHeader` when the record is an empty line.

### Removed

- Nothing

## [9.1.4] - 2018-05-01

### Added

- Nothing

### Deprecated

- Nothing

### Fixed

- `Writer::setFlushThreshold` should accept 1 as an argument [#289](https://github.com/thephpleague/csv/issue/289)
- `CharsetConverter::convert` should not try to convert numeric value [#287](https://github.com/thephpleague/csv/issue/287)

### Removed

- Nothing

## [9.1.3] - 2018-03-12

### Added

- Nothing

### Deprecated

- Nothing

### Fixed

- `Writer::insertOne` allow empty array to be added to the CSV (allow inserting empty row)
- Removed all return type from named constructor see [#285](https://github.com/thephpleague/csv/pull/285)
- Added PHPStan for static code analysis

### Removed

- Nothing

## 8.2.3 - 2018-02-06

### Added

- None

### Deprecated

- None

### Fixed

- `Reader::fetchAssoc` no longer throws exception because of a bug in PHP7.2+ [issue #279](https://github.com/thephpleague/csv/issues/279)

### Removed

- None

## [9.1.2] - 2018-02-05

### Added

- Nothing

### Deprecated

- Nothing

### Fixed

- `is_iterable` polyfill for PHP7.0
- `Reader::getHeader` no longer throws exception because of a bug in PHP7.2+ [issue #279](https://github.com/thephpleague/csv/issues/279)

### Removed

- Nothing

## [9.1.1] - 2017-11-28

### Added

- Nothing

### Deprecated

- Nothing

### Fixed

- issue with `error_get_last` usage when using a modified PHP error handler see [#254](https://github.com/thephpleague/csv/issues/254) - fixed by [@csiszarattila](https://github.com/csiszarattila)

- Removed seekable word from Stream exception messages.

### Removed

- Nothing

## [9.1.0] - 2017-10-20

### Added

- Support for non-seekable stream. When seekable feature are required an exceptions will be thrown.
- `League\Csv\EncloseField` to force enclosure insertion on every field. [#269](https://github.com/thephpleague/csv/pull/269)
- `League\Csv\EscapeFormula` a League CSV formatter to prevent CSV Formula Injection in Spreadsheet programs.
- `League\Csv\RFC4180Field::addTo` accept an option `$replace_whitespace` argument to improve RFC4180 compliance.
- `League\Csv\Abstract::getContent` to replace `League\Csv\Abstract::__toString`. The `__toString` method may trigger a Fatal Error with non-seekable stream, instead you are recommended to used the new `getContent` method which will trigger an exception instead.

### Deprecated

- `League\Csv\Abstract::__toString` use `League\Csv\Abstract::getContent` instead. the `__toString` triggers a Fatal Error when used on a non-seekable CSV document. use the `getContent` method instead which will trigger an exception instead.

### Fixed

- Bug fixes headers from AbstractCsv::output according to RFC6266 [#250](https://github.com/thephpleague/csv/issues/250)
- Make sure the internal source still exists before closing it [#251](https://github.com/thephpleague/csv/issues/251)
- Make sure the `Reader::createFromPath` default open mode is `r` see [#258](https://github.com/thephpleague/csv/pull/258) and [#266](https://github.com/thephpleague/csv/pull/266)

### Removed

- Nothing

## [9.0.1] - 2017-08-21

### Added

- Nothing

### Deprecated

- Nothing

### Fixed

- CSV controls not applied when calling Writer::insertOne

### Removed

- Nothing

## [9.0.0] - 2017-08-18

### Added

- Improved CSV Records selection
  - `League\Csv\Reader::getRecords` to access all CSV records
  - `League\Csv\Statement` provides a constraint builder to select CSV records.
  - `League\Csv\ResultSet` represents the result set of the selected CSV records.
  - `League\Csv\delimiter_detect` function to detect CSV delimiter character
- Improved CSV document header selection.
  - `League\Csv\Reader::getHeader`
  - `League\Csv\Reader::getHeaderOffset`
  - `League\Csv\Reader::setHeaderOffset`
- Improved CSV Records conversion
  - `League\Csv\CharsetConverter` converts CSV records charset.
  - `League\Csv\XMLConverter` converts CSV records into DOMDocument
  - `League\Csv\HTMLConverter` converts CSV records into HTML table.
- Improved Exception handling
  - `League\Csv\Exception` the default exception
  - `League\Csv\CannotInsertRecord`
- Improved CSV document output
  - `League\Csv\AbstractCsv::chunk` method to output the CSV document in chunk
  - `League\Csv\bom_match` function to detect BOM sequence in a given string
  - `League\Csv\ByteSequence` interface to decoupled BOM sequence from CSV documents
- Improved CSV records column count consistency on insertion
  - `League\Csv\ColumnConsistency`
- Improved CSV document flush mechanism on insertion
  - `League\Csv\Writer::setFlushThreshold`
  - `League\Csv\Writer::getFlushThreshold`
- Improve RFC4180 compliance
  - `League\Csv\RFC4180Field` to format field according to RFC4180 rules

### Deprecated

- Nothing

### Fixed

- Improved CSV record insertion
  - `League\Csv\Writer::insertOne` only accepts an array and returns a integer
  - `League\Csv\Writer::insertAll` only accepts an iterable of array and returns an integer

- Normalized CSV offset returned value
  - `League\Csv\Reader::fetchColumn` always returns the CSV document original offset.

### Removed

- `examples` directory
- `PHP5` support
- The following method is removed because The BOM API is simplified:
  - `League\Csv\AbstractCsv::stripBOM`
- All conversion methods are removed in favor of the conversion classes:
  - `League\Csv\Writer::jsonSerialize`
  - `League\Csv\AbstractCsv::toHTML`
  - `League\Csv\AbstractCsv::toXML`
  - `League\Csv\AbstractCsv::setInputEncoding`
  - `League\Csv\AbstractCsv::getInputEncoding`
- The following methods are removed because the PHP stream filter API is simplified:
  - `League\Csv\AbstractCsv::isActiveStreamFilter`
  - `League\Csv\AbstractCsv::setStreamFilterMode`
  - `League\Csv\AbstractCsv::appendStreamFilter`
  - `League\Csv\AbstractCsv::prependStreamFilter`
  - `League\Csv\AbstractCsv::removeStreamFilter`
  - `League\Csv\AbstractCsv::clearStreamFilters`
- The following methods are removed because switching between connections is no longer possible:
  - `League\Csv\AbstractCsv::newReader`
  - `League\Csv\AbstractCsv::newWriter`
  - `League\Csv\Reader::getNewline`
  - `League\Csv\Reader::setNewline`
- The Exception mechanism is improved thus the following class is removed:
  - `League\Csv\Exception\InvalidRowException`;
- The CSV records filtering methods are removed in favor of the `League\Csv\Statement` class:
  - `League\Csv\AbstractCsv::addFilter`,
  - `League\Csv\AbstractCsv::addSortBy`,
  - `League\Csv\AbstractCsv::setOffset`,
  - `League\Csv\AbstractCsv::setLimit`;
- CSV records selecting API methods is simplified:
  - `League\Csv\Reader::each`
  - `League\Csv\Reader::fetch`
  - `League\Csv\Reader::fetchAll`
  - `League\Csv\Reader::fetchAssoc`
  - `League\Csv\Reader::fetchPairsWithoutDuplicates`
- Formatting and validating CSV records on insertion is simplified, the following methods are removed:
  - `League\Csv\Writer::hasFormatter`
  - `League\Csv\Writer::removeFormatter`
  - `League\Csv\Writer::clearFormatters`
  - `League\Csv\Writer::hasValidator`
  - `League\Csv\Writer::removeValidator`
  - `League\Csv\Writer::clearValidators`
  - `League\Csv\Writer::getIterator`
- The following Formatters and Validators classes are removed from the package:
  - `League\Csv\Plugin\SkipNullValuesFormatter`
  - `League\Csv\Plugin\ForbiddenNullValuesValidator`
  - `League\Csv\Plugin\ColumnConsistencyValidator` *replace by `League\Csv\ColumnConsistency`*
- `League\Csv\Writer` no longers implements the `IteratorAggregate` interface
- `League\Csv\AbstractCsv::fetchDelimitersOccurrence` is removed *replace by `League\Csv\delimiter_detect` function*

## 8.2.2 - 2017-07-12

### Added

- None

### Deprecated

- None

### Fixed

- `Writer::insertOne` was silently failing when inserting record in a CSV document in non-writing mode.
- bug fix docblock

### Removed

- None

## 8.2.1 - 2017-02-22

### Added

- Nothing

### Deprecated

- Nothing

### Fixed

- internal `Reader::getRow` when using a `StreamIterator` [issue #213](https://github.com/thephpleague/csv/issues/213)
- Removed `@deprecated` from selected methods [issue #208](https://github.com/thephpleague/csv/issues/213)

### Removed

- Nothing

## 8.2.0 - 2017-01-25

### Added

- `AbstractCsv::createFromStream` to enable working with resource stream [issue #202](https://github.com/thephpleague/csv/issues/202)

### Deprecated

- `League\Csv\AbstractCsv::stripBom`
- `League\Csv\Reader::getOffset`
- `League\Csv\Reader::getLimit`
- `League\Csv\Reader::getSortBy`
- `League\Csv\Reader::getFilter`
- `League\Csv\Reader::setOffset`
- `League\Csv\Reader::setLimit`
- `League\Csv\Reader::addSortBy`
- `League\Csv\Reader::addFilter`
- `League\Csv\Reader::fetch`
- `League\Csv\Reader::each`
- `League\Csv\Reader::fetchPairsWithoutDuplicates`
- `League\Csv\Reader::fetchAssoc`
- `League\Csv\Writer::removeFormatter`
- `League\Csv\Writer::hasFormatter`
- `League\Csv\Writer::clearFormatters`
- `League\Csv\Writer::removeValidator`
- `League\Csv\Writer::hasValidator`
- `League\Csv\Writer::clearValidators`
- `League\Csv\Writer::jsonSerialize`
- `League\Csv\Writer::toHTML`
- `League\Csv\Writer::toXML`

### Fixed

- Nothing

### Removed

- Nothing

## 8.1.2 - 2016-10-27

### Added

- Nothing

### Deprecated

- Nothing

### Fixed

- BOM filtering fix [issue #184](https://github.com/thephpleague/csv/issues/184)
- `AbstractCsv::BOM_UTF32_LE` value fixed

### Removed

- Nothing

## 8.1.1 - 2016-09-05

### Added

- Nothing

### Deprecated

- Nothing

### Fixed

- `getInputBOM` method name is now consistent everywhere in the API [PR #171](https://github.com/thephpleague/csv/pull/171)
- preserve fileObject CSV controls [commit #8a20c56](https://github.com/thephpleague/csv/commit/8a20c56144effa552a8cba5d8c626063222975b7)
- Change `output` method header content-type value to `text/csv` [PR #175](https://github.com/thephpleague/csv/pull/175)

### Removed

- Nothing

## 8.1.0 - 2016-05-31

### Added

- The package now includes its own autoloader.
- `Ouput::getInputEncoding`
- `Ouput::setInputEncoding`

### Deprecated

- `Ouput::getEncodingFrom` replaced by `Ouput::getInputEncoding`
- `Ouput::setEncodingFrom` replaced by `Ouput::setInputEncoding`

### Fixed

- Stream Filters are now url encoded before usage [issue #72](https://github.com/thephpleague/csv/issues/72)
- All internal parameters are now using the snake case format

### Removed

- Nothing

## 8.0.0 - 2015-12-11

### Added

- `Reader::fetchPairs`
- `Reader::fetchPairsWithoutDuplicates`

### Deprecated

- Nothing

### Fixed

- `Reader::fetchColumn` and `Reader::fetchAssoc` now return `Iterator`
- `Reader::fetchAssoc` callable argument expects an indexed row using the submitted keys as its first argument
- `Reader::fetchColumn` callable argument expects the selected column value as its first argument
- Default value on `setOutputBOM` is removed
- `AbstractCsv::getOutputBOM` always return a string
- `AbstractCsv::getInputBOM` always return a string

### Removed

- `Controls::setFlags`
- `Controls::getFlags`
- `Controls::detectDelimiterList`
- `QueryFilter::removeFilter`
- `QueryFilter::removeSortBy`
- `QueryFilter::hasFilter`
- `QueryFilter::hasSortBy`
- `QueryFilter::clearFilter`
- `QueryFilter::clearSortBy`
- `Reader::query`
- The `$newline` argument from `AbstractCsv::createFromString`

## 7.2.0 - 2015-11-02

### Added

- `Reader::fetch` replaces `League\Csv\Reader::query` for naming consistency
- `Controls::fetchDelimitersOccurrence` to replace `Controls::detectDelimiterList` the latter gives erronous results

### Deprecated

- `Controls::detectDelimiterList`
- `Reader::query`
- The `$newline` argument from `AbstractCsv::createFromString`

### Fixed

- Streamming feature no longer trim filter name argument [issue #122](https://github.com/thephpleague/csv/issues/122)
- Fix default `SplFileObject` flags usage [PR #130](https://github.com/thephpleague/csv/pull/130)
- `AbstractCsv::createFromString` no longer trim the submitted string [issue #132](https://github.com/thephpleague/csv/issues/132)

### Removed

- Nothing

## 7.1.2 - 2015-06-10

### Added

- Nothing

### Deprecated

- Nothing

### Fixed

- Enclosures should be removed when a BOM sequence is stripped [issue #102](http://github.com/thephpleague/csv/issues/99)

### Removed

- Nothing

## 7.1.1 - 2015-05-20

### Added

- Nothing

### Deprecated

- Nothing

### Fixed

- `SplFileObject` flags were not always applied using query filter [issue #99](http://github.com/thephpleague/csv/issues/99)

### Removed

- Nothing

## 7.1.0 - 2015-05-06

### Added

- `stripBOM` query filtering method to ease removing the BOM sequence when querying the CSV document.
- All query filters are now accessible in the `Writer` class for conversion methods.

### Deprecated

- Nothing

### Fixed

- Internal code has been updated to take into account [issue #68479](http://bugs.php.net/68479)
- `setFlags` on conversion methods SplFileObject default flags are `SplFileObject::READ_AHEAD|SplFileObject::SKIP_EMPTY`
- `insertOne` now takes into account the escape character when modified after the first insert.

### Removed

- Nothing

## 7.0.1 - 2015-03-23

### Added

- Nothing

### Deprecated

- Nothing

### Fixed

- `setFlags`: `SplFileObject::DROP_NEW_LINE` can be remove using `setFlags` method.

### Removed

- Nothing

## 7.0.0 - 2015-02-19

### Added

- A new flexible mechanism to format and validate a row before its insertion by adding
  - `Writer::addFormatter` to add a formatter to the `Writer` object
  - `Writer::removeFormatter` to remove an already registered formatter
  - `Writer::hasFormatter` to detect the presence of a formatter
  - `Writer::clearFormatters` to clear all registered formatter
  - `Writer::addValidator` to add a validator to the `Writer` object
  - `Writer::removeValidator` to remove an already registered validator
  - `Writer::hasValidator` to detect the presence of a validator
  - `Writer::clearValidators` to clear all registered validator
  - `League\Csv\Exception\InvalidRowException` exception thrown when row validation failed
- Classes to maintain removed features from the `Writer` class
  - `League\Csv\Plugin\ColumnConsistencyValidator` to validate column consistency on insertion
  - `League\Csv\Plugin\ForbiddenNullValuesValidator` to validate `null` value on insertion
  - `League\Csv\Plugin\SkipNullValuesFormatter` to format `null` value on insertion

### Deprecated

- Nothing

### Fixed

- `jsonSerialize`, `toXML` and `toHTML` output can be modified using `Reader` query options methods.
- `AbstractCSV::detectDelimiterList` index keys now represents the occurrence of the found delimiter.
- `getNewline` and `setNewline` are accessible on the `Reader` class too.
- the named constructor `createFromString` now accepts the `$newline` sequence as a second argument to specify the last added new line character to better work with interoperability.
- Default value on CSV controls setter methods `setDelimiter`, `setEnclosure` and `setEscape` are removed
- Default `SplFileObject` flags value is now `SplFileObject::READ_CSV|SplFileObject::DROP_NEW_LINE`
- All CSV properties are now copied when using `newReader` and `newWriter` methods
- BOM addition on output improved by removing if found the existing BOM character
- the `AbstractCSV::output` method now returns the number of bytes send to the output buffer
- `Reader::fetchColumn` will automatically filter out non existing values from the return array

### Removed

- Setting `ini_set("auto_detect_line_endings", true);` is no longer set in the class constructor. Mac OS X users must explicitly set this ini options in their script.
- `Writer` and `Reader` default constructor are removed from public API in favor of the named constructors.
- All `Writer` methods and constant related to CSV data validation and formatting before insertion
  - `Writer::getNullHandlingMode`
  - `Writer::setNullHandlingMode`
  - `Writer::setColumnsCount`
  - `Writer::getColumnsCount`
  - `Writer::autodetectColumnsCount`
  - `Writer::NULL_AS_EXCEPTION`
  - `Writer::NULL_AS_EMPTY`
  - `Writer::NULL_AS_SKIP_CELL`

## 6.3.0 - 2015-01-21

### Added

- `AbstractCSV::setOutputBOM`
- `AbstractCSV::getOutputBOM`
- `AbstractCSV::getInputBOM`

to manage BOM character with CSV.

### Deprecated

- Nothing

### Fixed

- Nothing

### Removed

- Nothing

## 6.2.0 - 2014-12-12

### Added

- `Writer::setNewline` , `Writer::getNewline`  to control the newline sequence character added at the end of each CSV row.

### Deprecated

- Nothing

### Fixed

- Nothing

### Removed

- Nothing

## 6.1.0 - 2014-12-08

### Added

- `Reader::fetchAssoc` now also accepts an integer as first argument representing a row index.

### Deprecated

- Nothing

### Fixed

- Nothing

### Removed

- Nothing

## 6.0.1 - 2014-11-12

### Added

- Nothing

### Deprecated

- Nothing

### Fixed

- Bug Fixed `detectDelimiterList`

### Removed

- Nothing

## 6.0.0 - 2014-08-28

### Added

- Stream Filter API in `League\Csv\AbstractCsv`
- named constructors `createFromPath` and `createFromFileObject` in `League\Csv\AbstractCsv` to ease CSV object instantiation
- `detectDelimiterList` in `League\Csv\AbstractCsv` to replace and remove the use of `RuntimeException` in `detectDelimiter`
- `setEncodingFrom` and `setDecodingFrom` in `League\Csv\AbstractCsv` to replace `setEncoding` and `getEncoding` for naming consistency
- `newWriter` and `newReader` methods in `League\Csv\AbstractCsv` to replace `Writer::getReader` and `Reader::getWriter`

### Deprecated

- Nothing

### Fixed

- `League\Csv\Reader::each` more strict `$callable` MUST returns `true`

### Remove

- `League\Csv\AbstractCsv::detectDelimiter`
- `League\Csv\AbstractCsv::setEncoding` and `League\Csv\AbstractCsv::getEncoding`
- `League\Csv\Reader::setSortBy`
- `League\Csv\Reader::setFilter`
- `League\Csv\Reader::getWriter`
- `League\Csv\Writer::getReader`
- `League\Csv\Reader::fetchCol`

## 5.4.0 - 2014-04-17

### Added

- `League\Csv\Writer::setColumnsCount`, `League\Csv\Writer::getColumnsCount`, `League\Csv\Writer::autodetectColumnsCount` to enable column consistency in writer mode
- `League\Csv\Reader::fetchColumn` replaces `League\Csv\Reader::fetchCol` for naming consistency

### Deprecated

- `League\Csv\Reader::fetchCol`

### Fixed

- Nothing

### Removed

- Nothing

## 5.3.1 - 2014-04-09

### Added

- Nothing

### Deprecated

- Nothing

### Fixed

- `$open_mode` defaults to `r+` in `League\Csv\AbstractCsv` constructors

### Removed

- Nothing

## 5.3.0 - 2014-03-24

### Added

- `League\Csv\Writer::setNullHandlingMode` and `League\Csv\Writer::getNullHandlingMode` to handle `null` value

### Deprecated

- Nothing

### Fixed

- `setting ini_set("auto_detect_line_endings", true);` no longer needed for Mac OS

### Removed

- Nothing

## 5.2.0 - 2014-03-13

### Added

- `League\Csv\Reader::addSortBy`, `League\Csv\Reader::removeSortBy`, `League\Csv\Reader::hasSortBy`, `League\Csv\Reader::clearSortBy` to improve sorting
- `League\Csv\Reader::clearFilter` to align extract filter capabilities to sorting capabilities

### Deprecated

- `League\Csv\Reader::setSortBy` replaced by a better implementation

### Fixed

- `League\Csv\Reader::setOffset` now defaults to 0;
- `League\Csv\Reader::setLimit` now defaults to -1;
- `detectDelimiter` bug fixes

### Removed

- Nothing

## 5.1.0 - 2014-03-11

### Added

- `League\Csv\Reader::each` to ease CSV import data
- `League\Csv\Reader::addFilter`, `League\Csv\Reader::removeFilter`, `League\Csv\Reader::hasFilter` to improve extract filter capabilities
- `detectDelimiter` method to `League\Csv\AbstractCsv` to sniff CSV delimiter character.

### Deprecated

- `League\Csv\Reader::setFilter` replaced by a better implementation

### Fixed

- Nothing

### Removed

- Nothing

## 5.0.0 - 2014-02-28

### Added

- Change namespace from `Bakame\Csv` to `League\Csv`

### Deprecated

- Nothing

### Fixed

- Nothing

### Removed

- Nothing

## 4.2.1 - 2014-02-22

### Fixed

- `$open_mode` validation is done by PHP internals directly

### Removed

- Nothing

## 4.2.0 - 2014-02-17

### Added

- `toXML` method to transcode the CSV into a XML in `Bakame\Csv\AbstractCsv`

### Fixed

- `toHTML` method bug in `Bakame\Csv\AbstractCsv`
- `output` method accepts an optional `$filename` argument
- `Bakame\Csv\Reader::fetchCol` defaults to `$columnIndex = 0`
- `Bakame\Csv\Reader::fetchOne` defaults to `$offset = 0`

## 4.1.2 - 2014-02-14

### Added

- Move from `PSR-0` to `PSR-4` to autoload the library

## 4.1.1 - 2014-02-14

### Fixed

- `Bakame\Csv\Reader` methods fixed
- `jsonSerialize` bug fixed

## 4.1.0 - 2014-02-07

### Added

- `getEncoding` and `setEncoding` methods to `Bakame\Csv\AbstractCsv`

### Fixed

- `Bakame\Csv\Writer::insertOne` takes into account CSV controls
- `toHTML` method takes into account encoding

## 4.0.0 - 2014-02-05

### Added

- `Bakame\Csv\Writer`
- `Bakame\Csv\Writer` and `Bakame\Csv\Reader` extend `Bakame\Csv\AbstractCsv`

### Deprecated

- Nothing

### Fixed

- `Bakame\Csv\Reader::fetchOne` is no longer deprecated
- `Bakame\Csv\Reader::fetchCol` no longer accepts a third parameter `$strict`

### Removed

- `Bakame\Csv\Codec` now the library is composer of 2 main classes
- `Bakame\Csv\Reader::getFile`
- `Bakame\Csv\Reader::fetchValue`
- `Bakame\Csv\Reader` no longer implements the `ArrayAccess` interface

## 3.3.0 - 2014-01-28

### Added

- `Bakame\Csv\Reader` implements `IteratorAggregate` Interface
- `Bakame\Csv\Reader::createFromString` to create a CSV object from a raw string
- `Bakame\Csv\Reader::query` accept an optional `$callable` parameter

### Deprecated

- `Bakame\Csv\Reader::getFile` in favor of `Bakame\Csv\Reader::getIterator`

### Removed

- `Bakame\Csv\ReaderInterface` useless interface

### Fixed

- `Bakame\Csv\Reader::fetch*` `$callable` parameter is normalized to accept an array
- `Bakame\Csv\Reader::fetchCol` accepts a third parameter `$strict`

## 3.2.0 - 2014-01-16

### Added

- `Bakame\Csv\Reader` implements the following interfaces `JsonSerializable` and `ArrayAccess`
- `Bakame\Csv\Reader::toHTML` to output the CSV as a HTML table
- `Bakame\Csv\Reader::setFilter`, `Bakame\Csv\Reader::setSortBy`, `Bakame\Csv\Reader::setOffset`, `Bakame\Csv\Reader::setLimit`, `Bakame\Csv\Reader::query` to perform SQL like queries on the CSV content.
- `Bakame\Csv\Codec::setFlags`, `Bakame\Csv\Codec::getFlags`, Bakame\Csv\Codec::__construct : add an optional `$flags` parameter to enable the use of `SplFileObject` constants flags

### Deprecated

- `Bakame\Csv\Reader::fetchOne` replaced by `Bakame\Csv\Reader::offsetGet`
- `Bakame\Csv\Reader::fetchValue` useless method

## 3.1.0 - 2014-01-13

### Added

- `Bakame\Csv\Reader::output` output the CSV data directly in the output buffer
- `Bakame\Csv\Reader::__toString` can be use to echo the raw CSV

## 3.0.1 - 2014-01-10

### Fixed

- `Bakame\Csv\Reader::fetchAssoc` when users keys and CSV row data don't have the same length

## 3.0.0 - 2014-01-10

### Added

- `Bakame\Csv\ReaderInterface`
- `Bakame\Csv\Reader` class

### Fixed

- `Bakame\Csv\Codec::loadString`returns a `Bakame\Csv\Reader` object
- `Bakame\Csv\Codec::loadFile` returns a `Bakame\Csv\Reader` object
- `Bakame\Csv\Codec::save` returns a `Bakame\Csv\Reader` object

## 2.0.0 - 2014-01-09

### Added

- `Bakame\Csv\CsvCodec` class renamed `Bakame\Csv\Codec`

### Deprecated

- Nothing

### Fixed

- Nothing

### Removed

- `Bakame\Csv\Codec::create` from public API

## 1.0.0 - 2013-12-03

Initial Release of `Bakame\Csv`

[Next]: https://github.com/thephpleague/csv/compare/9.12.0...master
[9.10.0]: https://github.com/thephpleague/csv/compare/9.9.0...9.10.0
[9.9.0]: https://github.com/thephpleague/csv/compare/9.8.0...9.9.0
[9.8.0]: https://github.com/thephpleague/csv/compare/9.7.4...9.8.0
[9.7.4]: https://github.com/thephpleague/csv/compare/9.7.3...9.7.4
[9.7.3]: https://github.com/thephpleague/csv/compare/9.7.2...9.7.3
[9.7.2]: https://github.com/thephpleague/csv/compare/9.7.1...9.7.2
[9.7.1]: https://github.com/thephpleague/csv/compare/9.7.0...9.7.1
[9.7.0]: https://github.com/thephpleague/csv/compare/9.6.2...9.7.0
[9.6.2]: https://github.com/thephpleague/csv/compare/9.6.1...9.6.2
[9.6.1]: https://github.com/thephpleague/csv/compare/9.6.0...9.6.1
[9.6.0]: https://github.com/thephpleague/csv/compare/9.5.0...9.6.0
[9.5.0]: https://github.com/thephpleague/csv/compare/9.4.1...9.5.0
[9.4.1]: https://github.com/thephpleague/csv/compare/9.4.0...9.4.1
[9.4.0]: https://github.com/thephpleague/csv/compare/9.3.0...9.4.0
[9.3.0]: https://github.com/thephpleague/csv/compare/9.2.1...9.3.0
[9.2.1]: https://github.com/thephpleague/csv/compare/9.2.0...9.2.1
[9.2.0]: https://github.com/thephpleague/csv/compare/9.1.4...9.2.0
[9.1.4]: https://github.com/thephpleague/csv/compare/9.1.3...9.1.4
[9.1.3]: https://github.com/thephpleague/csv/compare/9.1.2...9.1.3
[9.1.2]: https://github.com/thephpleague/csv/compare/9.1.1...9.1.2
[9.1.1]: https://github.com/thephpleague/csv/compare/9.1.0...9.1.1
[9.1.0]: https://github.com/thephpleague/csv/compare/9.0.1...9.1.0
[9.0.1]: https://github.com/thephpleague/csv/compare/9.0.0...9.0.1
[9.0.0]: https://github.com/thephpleague/csv/compare/8.2.2...9.0.0
