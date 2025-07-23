# short-uuid

[![Maven Central Version](https://img.shields.io/maven-central/v/ai.bizone/short-uuid)](https://central.sonatype.com/artifact/ai.bizone/short-uuid)
[![javadoc](https://javadoc.io/badge2/ai.bizone/short-uuid/javadoc.svg)](https://javadoc.io/doc/ai.bizone/short-uuid)
[![Build](https://github.com/bizone-ai/short-uuid/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/bizone-ai/short-uuid/actions/workflows/ci.yml)
[![GitHub Release](https://img.shields.io/github/v/release/bizone-ai/short-uuid)](https://github.com/bizone-ai/short-uuid/releases)
[![License](https://img.shields.io/github/license/bizone-ai/short-uuid)](./LICENSE)

Short UUID conversion and generation library for Java.
- Can make a UUID shorter in string format (down to 22 characters)

## Installation

Maven
```xml
<dependency>
    <groupId>ai.bizone</groupId>
    <artifactId>short-uuid</artifactId>
</dependency>
```

Gradle
```groovy
implementation 'ai.bizone:short-uuid'
```

## Usage Example

```java
import ai.bizone.shortuuid.ShortUuid;

public class Main {
    public static void main(String[] args) {
        String a = ShortUuid.random(false /* Use Base36 */);
        System.out.println(a);
        // e.g. "bazl2kp9io74mfdaid40j6xia"
        
        String b = ShortUuid.random(true /* Use Base62 */);
        System.out.println(b);
        // e.g. "2RGPvdeVim1yS4rHlLpN9f"
        
        // You can also convert a UUID to Base64 (URL)
        String c = UuidConverter.toBase64(UUID.randomUUID());
        System.out.println(c);
        
        // Shorten an existing UUID
        String d = UuidConverter.toShortUuid(UUID.randomUUID(), true /* Use Base62 */);
        System.out.println(d);
    }
}
```

See tests for more examples.

## License

[Apache License 2.0](./LICENSE)
