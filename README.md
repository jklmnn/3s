# 3s

3s (simple site (with) sed) is a very simple static site generator written in bash with sed.
It is only able to replace basic tokens. Tokens should be ascii only
(ar at least do not contain characters used by sed). It is not intended to fill the whole
content of a web page but to replace short but often used identifiers such as names and domains.

## HTML Template

The template syntax is quite simple, it uses double brackets to mark tokens:
```HTML
<html>
    <head>
        <title>{{name}}</title>
    </head>
    <body>
        <h1>{{name}}</h1>
    </body>
</html>
```

## Token definition

The template directory should contain a file named `.3s` with contains lines of `key:value` pairs:
```
name:My Simple Website
```

## Usage

3s should be called with the input and the output directory:
```
$ ./3s /path/to/input /path/to/output
```

3s will copy all non hidden files to the new directory and recreate the original directory structure.
Tokens in HTML files will then be changed in place.
