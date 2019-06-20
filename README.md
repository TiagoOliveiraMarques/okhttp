OkHttp
======

An HTTP & HTTP/2 client for Android and Java applications.

See the [**project website**][website] for documentation and APIs.


Requirements
------------

OkHttp works on Android 5.0+ (API level 21+) and on Java 8+.

OkHttp has one library dependency on [Okio][okio], a small library for high-performance I/O.

We highly recommend you keep OkHttp up-to-date. As with auto-updating web browsers, staying current
with HTTPS clients is an important defense against potential security problems. [We
track][tls_history] the dynamic TLS ecosystem and adjust OkHttp to improve connectivity and
security.

OkHttp uses your platform's built-in TLS implementation. On Java platforms OkHttp also supports
[Conscrypt][conscrypt], which integrates BoringSSL with Java. OkHttp will use Conscrypt if it is
the first security provider:

```java
Security.insertProviderAt(Conscrypt.newProvider(), 1);
```

The OkHttp 3.12.x branch supports Android 2.3+ (API level 9+) and Java 7+. These platforms lack
support for TLS 1.2 and should not be used. But because upgrading is difficult we will backport
critical fixes to the [3.12.x branch][okhttp_312x] through December 31, 2020.

Releases
--------

Our [change log](CHANGELOG.md) has release history.

```kotlin
implementation("com.squareup.okhttp3:okhttp:3.14.2")
```

Snapshot builds are [available][snap].


MockWebServer
-------------

OkHttp includes a library for testing HTTP, HTTPS, and HTTP/2 clients.

```kotlin
testImplementation("com.squareup.okhttp3:mockwebserver:3.14.2")
```

R8 / ProGuard
-------------

If you are using R8 or ProGuard add the options from [`okhttp3.pro`][okhttp3_pro].

You might also need rules for Okio which is a dependency of this library.


License
-------

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.


 [conscrypt]: https://github.com/google/conscrypt/
 [okhttp_312x]: https://github.com/square/okhttp/tree/okhttp_3.12.x
 [okio]: https://github.com/square/okio/
 [snap]: https://oss.sonatype.org/content/repositories/snapshots/
 [tls_history]: https://square.github.io/okhttp/tls_configuration_history/
 [website]: https://square.github.io/okhttp
 [okhttp3_pro]: https://github.com/square/okhttp/blob/master/okhttp/src/main/resources/META-INF/proguard/okhttp3.pro
