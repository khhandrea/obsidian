---
created-at: "2023-09-12T12:00:00"
tags:
  - note
description: Obsidian markdown 정리
---
# Obsidian Markdowns
## Todo
- Write all features
## Headings
```
# Heading 1
## Heading 2
### Heading 3
#### Heading 4
##### Heading 5
###### Heading 6
```

## Styled text
- **Bold**
	- `**Bold**`
	- Ctrl + B
- *Italic*
	- `*Italic*`
	- Cmd + I
- ***Bold and italic***
	- `***Bold and italic***`
- ~~Strikethrough~~
	- `~~Strikethrough~~`
- ==Highlight==
	- `"==Highlight==" (without quotes)`

## Quotes
```
> Quote message
```

> Quote message

## Callouts 
```ad-tip
title: This is a tip

This is the content
```



```
> [!info] (title)
> Message
```

```
> [!info]-(title)
> Foldable callout
```

```
> [!info]-(outer title)
> > [!info]-(inner title)
> > Nested callout
```

> [!info] info
> This is an information.

> [!todo] todo
> This is a todo.

> [!tip] tip, hint, important
> This is a tip.

> [!success] success, check, done
> This is a success.

> [!failure] failure, fail, missing 
> This is a failure.

> [!question] question, help, faq
> Is this a question?

> [!warning] warning, caution, attention
> This is a warning.

> [!danger] danger, error
> This is a danger.

> [!bug]
> This is a bug!

> [!example]
> This is an example.

> [!quote] quote, cite
> This is a quote.


## Comments
```
%%
Invisible in reading view
%%
```

%%
Invisible 
%%

## Footnotes
```
This[^1] is a simple[^2] footnote[^note].
It only works in reading view. ^[Inline footnotes. Caret outside the brackets. Looks number]

[^1]: Referenced text
[^note]: Named footnote(but looks number)
```

This[^1] is a simple[^2] footnote[^note].
It only works in reading view. ^[Inline footnotes. Caret outside the brakets. Looks number]


[^1]: Referenced text
[^2]: Referenced text
[^note]: Named footnote(but looks number)

