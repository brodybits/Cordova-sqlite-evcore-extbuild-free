# Changes

# cordova-sqlite-evcore-extbuild-free 0.9.2

## cordova-sqlite-storage 2.2.0

- Fix SQLiteAndroidDatabase implementation for Turkish and other foreign locales

## cordova-sqlite-storage 2.1.0

- Visual Studio 2017 updates for Windows UWP build

# cordova-sqlite-evcore-extbuild-free 0.9.1

- cordova-sqlite-evcore-common-free compile-time option fixes for iOS/macOS:
  - SQLITE_THREADSAFE=2 on iOS/macOS to avoid possible malformed database due to multithreaded access ref: <https://github.com/litehelpers/Cordova-sqlite-storage/issues/703>
  - Suppress warnings when building sqlite3.c (iOS/macOS)
  - Remove unwanted SQLITE_OMIT_BUILTIN_TEST option (iOS/macOS)
- Android evcore-native-driver NDK build in JAR from <https://github.com/litehelpers/Android-sqlite-evcore-native-driver-free/tree/ext-master> (with FTS5/JSON1/SQLITE_DEFAULT_PAGE_SIZE/SQLITE_DEFAULT_CACHE_SIZE build fixes included), wth JSMN (http://zserge.com/jsmn.html) included again under MIT license, now supports cordova-android@7.
- additional doc fixes

## cordova-sqlite-evcore-common-free 0.7.6

##### cordova-sqlite-legacy-core 1.0.7

- Add error info text in case of close error on Windows
- Signal INTERNAL ERROR in case of attempt to reuse db on Windows (should never happen due to workaround solution to BUG 666)

###### cordova-sqlite-legacy-express-core 1.0.5

- iOS/macOS @synchronized guard for sqlite3_open operation
- Signal INTERNAL ERROR in case of attempt to reuse db (Android/iOS) (should never happen due to workaround solution to BUG 666)

##### cordova-sqlite-legacy-core 1.0.6

###### cordova-sqlite-legacy-express-core 1.0.4

- Cleaned up workaround solution to BUG 666: close db before opening (ignore close error)
- android.database end transaction if active before closing (needed for new BUG 666 workaround solution to pass selfTest in case of builtin android.database implementation)

##### cordova-sqlite-legacy-core 1.0.5

###### cordova-sqlite-legacy-express-core 1.0.3

- Resolve Java 6/7/8 concurrent map compatibility issue reported in litehelpers/Cordova-sqlite-storage#726, THANKS to pointer by @NeoLSN (Jason Yang/楊朝傑) in litehelpers/Cordova-sqlite-storage#727.
- selfTest database cleanup do not ignore close or delete error on any platforms

##### cordova-sqlite-legacy-core 1.0.4

- New workaround solution to BUG 666: close db before opening (ignore close error)

##### cordova-sqlite-legacy-core 1.0.3

- Suppress warnings when building sqlite3.c & PSPDFThreadSafeMutableDictionary.m on iOS/macOS

##### cordova-sqlite-legacy-core 1.0.2

- Fix log in case of transaction waiting for open to finish; doc fixes
- Windows 10 (UWP) build with /SAFESEH flag on Win32 (x86) target

###### cordova-sqlite-legacy-express-core 1.0.2

- Use PSPDFThreadSafeMutableDictionary for iOS/macOS to avoid threading issue ref: litehelpers/Cordova-sqlite-storage#716

###### cordova-sqlite-legacy-express-core 1.0.1

- Fix bug 666 workaround to trigger ROLLBACK in the next event tick (needed to support version with pre-populated database on Windows)

# cordova-sqlite-evcore-extbuild-free 0.9.0

NOTICE: cordova-sqlite-evcore-extbuild-free releases 0.8.5, 0.8.6, 0.8.7, and 0.9.0 include evcore-native-driver build with missing source; a special GPL v3 exception is granted for these releases as described in <https://github.com/litehelpers/Cordova-sqlite-evcore-extbuild-free/issues/24>.

## cordova-sqlite-storage 2.0.4

## cordova-sqlite-storage 2.0.3

- Drop engines rule from package.json
- Doc fixes

## cordova-sqlite-storage 2.0.2

- Fix Windows target platform version

### cordova-sqlite-storage 2.0.0

- Reference Windows platform toolset v141 to support Visual Studio 2017 (RC)

# cordova-sqlite-evcore-extbuild-free 0.8.7

NOTICE: cordova-sqlite-evcore-extbuild-free releases 0.8.5, 0.8.6, 0.8.7, and 0.9.0 include evcore-native-driver build with missing source; a special GPL v3 exception is granted for these releases as described in <https://github.com/litehelpers/Cordova-sqlite-evcore-extbuild-free/issues/24>.

## cordova-sqlite-evcore-common-free 0.7.5

###### cordova-sqlite-legacy-express-core 1.0.0

- Workaround solution to BUG litehelpers/Cordova-sqlite-storage#666 (hanging transaction in case of location reload/change)
- selfTest simulate scenario & test solution to BUG litehelpers/Cordova-sqlite-storage#666 (also includes string test and test of effects of location reload/change in this version branch, along with another internal check)
- Drop engine constraints in package.json & plugin.xml (in this version branch)

# cordova-sqlite-evcore-extbuild-free 0.8.6

NOTICE: cordova-sqlite-evcore-extbuild-free releases 0.8.5, 0.8.6, 0.8.7, and 0.9.0 include evcore-native-driver build with missing source; a special GPL v3 exception is granted for these releases as described in <https://github.com/litehelpers/Cordova-sqlite-evcore-extbuild-free/issues/24>.

## cordova-sqlite-evcore-common-free 0.7.4

- Minor doc fixes

### cordova-sqlite-storage 1.5.4

- Fix iOS/macOS version to report undefined insertId in case INSERT OR IGNORE is ignored
- Fix FIRST_WORD check for android.sqlite.database implementation
- Doc updates

### cordova-sqlite-storage 1.5.3

- Fix merges to prevent possible conflicts with other plugins (Windows)
- Fix handling of undefined SQL argument values (Windows)
- Signal error in case of a failure opening the database file (iOS/macOS)
- Doc fixes and updates

# cordova-sqlite-evcore-extbuild-free 0.8.5

NOTICE: cordova-sqlite-evcore-extbuild-free releases 0.8.5, 0.8.6, 0.8.7, and 0.9.0 include evcore-native-driver build with missing source; a special GPL v3 exception is granted for these releases as described in <https://github.com/litehelpers/Cordova-sqlite-evcore-extbuild-free/issues/24>.

- Fix openDatabase/deleteDatabase exception messages in this version branch
- Build (with SQLite 3.15.2) with the following defines:
  - SQLITE_TEMP_STORE=2
  - SQLITE_THREADSAFE=1
  - SQLITE_ENABLE_FTS3
  - SQLITE_ENABLE_FTS3_PARENTHESIS
  - SQLITE_ENABLE_FTS4
  - SQLITE_ENABLE_FTS5
  - SQLITE_ENABLE_RTREE
  - SQLITE_ENABLE_JSON1
  - SQLITE_OMIT_BUILTIN_TEST
  - SQLITE_OMIT_LOAD_EXTENSION
  - SQLITE_DEFAULT_PAGE_SIZE=4096 and SQLITE_DEFAULT_CACHE_SIZE=-2000 - new stable page/cache sizes from 3.12.0 ref:
    - <http://sqlite.org/pgszchng2016.html>
    - <http://sqlite.org/releaselog/3_12_0.html>
  - SQLITE_OS_WINRT for Windows only
- Android version with JSMN (http://zserge.com/jsmn.html) dependency removed.
- Doc updates

### cordova-sqlite-storage 1.5.2

- Check transaction callback functions to avoid crash on Windows
- Fix echoTest callback handling
- Move Lawnchair adapter to a separate project
- Doc updates

# cordova-sqlite-evcore-extbuild-free 0.8.4

### cordova-sqlite-ext-common 0.1.0

- BASE64 support

### cordova-sqlite-ext-common 0.0.1

- REGEXP for Android/iOS/macOS using sqlite3-regexp-cached

# cordova-sqlite-evcore-extbuild-free 0.8.3

- Use SQLite 3.15.2 for all platforms (no SQLITE_DEFAULT_PAGE_SIZE or SQLITE_DEFAULT_CACHE_SIZE defined in this version branch)

## cordova-sqlite-evcore-common-free 0.7.3

- empty engines rule in package.json in this version branch

### cordova-sqlite-storage 1.5.1

- Add engines rule to package.json (...)

### cordova-sqlite-storage 1.5.0

- Drop support for Windows 8.1 & Windows Phone 8.1

### cordova-sqlite-storage 1.4.9

- Minor JavaScript fix (generated by CoffeeScript 1.11.1)
- Update test due to issue with u2028/u2029 on cordova-android 6.0.0
- doc fixes
- Cleanup plugin.xml: remove old engine constraint that was already commented out
- Fix LICENSE.md

# cordova-sqlite-evcore-extbuild-free 0.8.2

- Quick fix for Android error mapping and reporting
- Fix default Android implementation to reject SQL with too many parameters

## cordova-sqlite-evcore-common-free 0.7.2

- Fix Android version to handle location reload/change properly

### cordova-sqlite-storage 1.4.8

- selfTest function add string test and test of effects of location reload/change
- Support macOS ("osx" platform)
- Signal an error in case of SQL with too many parameter argument values on iOS (in addition to Android & Windows)
- Include proper SQL error code on Android (in certain cases)
- Fix reporting of SQL statement execution errors in Windows version
- Fix Windows version to report errors with a valid error code (0)
- Some doc fixes

### cordova-sqlite-storage 1.4.7

- Minor JavaScript fixes to pass @brodybits/Cordova-sql-test-app

## cordova-sqlite-evcore-common-free 0.7.1

# cordova-sqlite-evcore-extbuild-free 0.8.1

- Custom Android database file location
- Include SQLite 3.14 for iOS and Windows (without FTS5 or JSON1 enabled)

## cordova-sqlite-evcore-common-free 0.7.1

### cordova-sqlite-storage 1.4.6

- Stop remaining transaction callback in case of an error with no error handler returning false
- Expand selfTest function to cover CRUD with unique record keys
- Fix readTransaction to reject ALTER, REINDEX, and REPLACE operations
- Fix Windows 10 ARM Release Build of SQLite3 by disabling SDL check (ARM Release only)
- Fix Windows 8.1/Windows Phone 8.1 Release Build of SQLite3 by disabling SDL check
- Some documentation fixes

### cordova-sqlite-storage 1.4.5

- Log/error message fixes; remove extra qid from internal JSON interface

### cordova-sqlite-storage 1.4.4

- Fix readTransaction to reject modification statements with extra semicolon(s) in the beginning
- Announce new Cordova-sqlite-evcore-extbuild-free version
- Additional tests
- Other doc fixes

# cordova-sqlite-evcore-extbuild-free 0.8.0

- SQLite and Android-sqlite-evcore-native-driver-free dependencies included to support PhoneGap Build
- Cordova engines specification dropped from package.json

## cordova-sqlite-evcore-free 0.7.0

- Use Android-sqlite-evcore-native-driver-free for high performance and memory improvements on Android

### cordova-sqlite-storage 1.4.3

- Handle executeSql with object sql value (solves another possible crash on iOS)

### cordova-sqlite-storage 1.4.2

- Fix sqlitePlugin.openDatabase and sqlitePlugin.deleteDatabase to check location/iosDatabaseLocation values
- Fix sqlitePlugin.deleteDatabase to check that db name is really a string (prevents possible crash on iOS)
- Fix iOS version to use DLog macro to remove extra logging from release build
- Fix Lawnchair adapter to use new mandatory "location" parameter
- Remove special handling of Blob parameters, use toString for all non-value parameter objects
- Minor cleanup of Android version code

### cordova-sqlite-storage 1.4.1

- Minimum Cordova version no longer enforced in this version

### cordova-sqlite-storage 1.4.0

- Now using cordova-sqlite-storage-dependencies for SQLite 3.8.10.2 Android/iOS/Windows
- Android-sqlite-connector implementation supported by this version again
- Enforce minimum cordova-windows version (should be OK in Cordova 6.x)
- Support Windows 10 along with Windows 8.1/Windows Phone 8.1

### cordova-sqlite-storage 1.2.2

- Self-test function to verify ability to open/populate/read/delete a test database
- Read BLOB as Base-64 DISABLED in Android version (was already disabled for iOS)

### cordova-sqlite-storage 1.2.1

- Close Android SQLiteStatement after INSERT/UPDATE/DELETE
- Specify minimum Cordova version 6.0.0
- Lawnchair adapter fix: Changed remove method to work with key array

### cordova-sqlite-storage 1.2.0

- Rename Lawnchair adapter to prevent clash with standard webkit-sqlite adapter
- Support location: 'default' setting in openDatabase & deleteDatabase

### cordova-sqlite-storage 0.8.5

- More explicit iosDatabaseLocation option
- iOS database location is now mandatory
- Split-up of some more spec test scripts

### cordova-sqlite-storage 0.8.2

- Workaround fix for empty readTransaction issue (litehelpers/Cordova-sqlite-storage#409)
- Split spec/www/spec/legacy.js into db-open-close-delete-test.js & tx-extended.js

### cordova-sqlite-storage 0.8.0

- Simple sql batch transaction function
- Echo test function
- All iOS operations are now using background processing (reported to resolve intermittent problems with cordova-ios@4.0.1)
- Java source of Android version now using io.sqlc package
- Drop Android-sqlite-connector support
- Drop WP(8) and Windows support

### 0.7.14

- REGEXP support completely removed from this version branch
- Remove src/android/libs/.gitignore (inadvertently added in 0.7.13)

### 0.7.13

- REGEXP support partially removed from this version branch
- Rename Windows C++ Database close function to closedb to resolve conflict for Windows Store certification
- Android version with sqlite `3.8.10.2` embedded (with error messages fixed)
- Pre-populated database support removed from this version branch
- Amazon Fire-OS support removed
- Fix conversion warnings in iOS version

### 0.7.12

- Fix to Windows "Universal" version to support big integers
- Implement database close and delete operations for Windows "Universal"
- Fix readTransaction to skip BEGIN/COMMIT/ROLLBACK

### 0.7.11

- Fix plugin ID in plugin.xml to match npm package ID
- Unpacked sqlite-native-driver.so libraries from jar
- Fix conversion of INTEGER type (iOS version)
- Disable code to read BLOB as Base-64 (iOS version) due to https://issues.apache.org/jira/browse/CB-9638

### 0.7.10

- Use Android-sqlite-connector instead of sqlite4java

### 0.7.9

- Build iOS and Windows versions with sqlite 3.8.10.2 embedded
- Fix plugin id to match npm package id

### 0.7.8

- Support FTS3/FTS4 and R-Tree in iOS and Windows "Universal" (8.1) versions
- Build ARM target with Function Level Linking ref: http://www.monkey-x.com/Community/posts.php?topic=7739
- SQLite3.Windows.vcxproj and SQLite3.WindowsPhone.vcxproj in their own directories to avoid problems due to temporary files

### 0.7.7

- include build of sqlite4java for Android x86_64 and arm-64
- clean publish to plugins.cordova.io

### 0.7.6

- Small fix to plugin id
- Disable use of gethostuuid() in sqlite3.c (only used in iOS version)
- published to plugins.cordova.io - [BUG] published extra junk in workarea, causing problems with Windows (Universal) version

### 0.7.5

- Windows (Universal) version now supports both Windows 8.1 and Windows Phone 8.1
- iOS and Windows versions are now built with sqlite 3.8.9 embedded
- Improved locking style and other optimizations applied for iOS version

### 0.7.4

- iOS and Windows (8.1) versions built to keep non-essential temporary sqlite files in memory
- Option to use legacy Android database library, with Android locking/closing issue (BUG #193) workaround included again

### 0.7.3

- insertId & rowsAffected implemented for Windows (8.1)
- plugin id changed

### 0.7.2

- Android version with sqlite4java (sqlite 3.8.7 embedded), which solves BUG #193: Android closing/locking issue (ICU-UNICODE integration is now missing)
- iOS version fixed to override the correct pluginInitialize method and built with sqlite 3.8.8.3 embedded

### 0.7.1

- Project renamed
- Initial version for Windows (8.1) [with sqlite 3.8.8.3 embedded]
- Abort initially pending transactions for db handle (due to incorrect password key, for example) [from Cordova-sqlcipher-storage]
- WP7 build enabled (NOT TESTED)

### 1.0.6

- Proper handling of transactions that may be requested before the database open operation is completed
- Report an error upon attempt to close a database handle object multiple times.

### 1.0.5

- Workaround for Android db locking/closing issue
- Fix double-precision REAL values in result (iOS version)
- Fix query result truncation in case of NULL character (\0 or \u0000) (iOS version)
- Convert array SQL parameters to string, according to match Web SQL spec
- Fix closing of Android database
- Some fixes for SQL API error handling to be consistent with Web SQL

### 1.0.4

- Pre-populated database option (Android/iOS)
- Option to select database location to disable iCloud backup (iOS ONLY)
- Safeguard against closing of database while transaction is pending
- Fix to prevent double marshaling of data

### 1.0.3

- Fixed issue with multi-page apps on Android (due to problem when closing & re-opening app)

### 1.0.2

- Workaround for issue with multiple UPDATE statements WP(8) (#128)

### 1.0.1

- Support Cordova 3.3.0/3.4.0 to support Amazon-FireOS
- Fixes for WP(8):
  - use one thread per db to solve open/close/delete issues
  - fix integer data binding
- Fix open/close callbacks Android & WP(8)
- Resolve issue with INSERT OR IGNORE (Android)
