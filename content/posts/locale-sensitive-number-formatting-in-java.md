---
title: "Locale-Sensitive Number Formatting in Java"
date: 2024-08-15
tags: [ 'java', 'gotcha' ]
draft: false
---

### Locale-Sensitive Number Formatting in Java

While working on a piece of code, I encountered an issue that I thought was worth sharing. The task seemed straightforward: generate a file path that includes an integer ID. Here's a simplified version of the code:

```java
// id - arbitrary integer
int id = 123;
// Expected output: /tmp/app-files/123
String path = String.format(Locale.getDefault(), "/tmp/app-files/%d", id);

```

At first glance, this looks simple and works fine—**as long as your locale uses [Western Arabic Numerals](https://en.wikipedia.org/wiki/Arabic_numerals)** (Unicode/ASCII 0x30 to 0x39). However, things take an unexpected turn when your locale uses a different numeral system, such as Bengali.

For instance, the Bengali numerals are:

```
০	১	২	৩	৪	৫	৬	৭	৮	৯
```

If your locale is set to Bengali, the generated path would look like:

```bash
/tmp/app-files/১২৩
```

This output might not be what you expected, especially if you require the path to strictly use Western Arabic numerals.

### The Solution: Use Locale.US
To avoid this issue and ensure consistent formatting across different locales, it's better to use `Locale.US` when formatting numbers for paths or similar cases where the output should remain consistent regardless of the user's locale:

```java
String path = String.format(Locale.US, "/tmp/app-files/%d", id);
```

Now, regardless of the locale, the path will be correctly formatted as:

```bash
/tmp/app-files/123
```

This approach ensures that your code behaves predictably in environments with different locale settings.

Thanks for reading!