# Basics

## Dot - for any character

`.` : represents any character.

`b.g`

*The **big** **bag** of bits was **bug**ged.*

`.` : just matches only a single character. To match **more than** a single character using multipliers.

`l..e`

*You can **live** **like** a king but make sure it isn't a lie.*

## Ranges of characters

`t[eo]d` : starts with `t`, followed by either the character `e`, or `o`, ends with `d`

*When **tod**ay is over T**ed** will have a **ted**ious time tidying up.*

## Shortcut

`[12345678]` : shortcut -> `[1-8]`

`[1-49]` : searching for 1, 2, 3, 4, 9

Room Allocations: G**4**, G**9**, F**2**, H**1**, L0, K**7**, M**9**

If we want to search for 1, 2, 3, 4, 5, a, b, c, d, e, f, x -> `[1-5a-fx]`

### Warning

Sometimes, using sets of characters lead to od d behaviour. `[a-f]` may match `D`. Because most systems have a character table where all the lowercase letters come first, then the uppercase letters, like `abcdef...xyzABCD...`. A few systems however, alternate the lowercase and uppercase letters, like `aAbBcCdD...yYzZ`.



## Negating - Find characters that aren't

If you want to find the presence of a character which is not a range of characters, we can use caret `^`.

`t[^eo]d` : start with `t`, followed by a character which is not either `e` or `o`, ends with `d`.  

## Multipliers

* `*` : item occurs zero or more times.
* `+` : item occurs one or more times.
* `?` : item occurs zero or one times.
* `{5}` : item occurs five times.
* `{3, 7}` : item occurs between 3 and 7 times.
* `{2,}` : item occurs at least 2 times.

`lo*`

*Are you **looking** at the **lock** or the si**l**k?*

In the above example we are looking for the character `l` followed by the character `o` zero or more times. That is why the `l` in `silk` is also matched

## Escaping metacharacters

If we want to search for one of the characters which is a metacharacter. By placing `\` in front of a metacharacter we can remove it's special meaing.

`this.` : `.` full stop in the regular expression normally matches any character.

Surely **this** regular expression should match **this.** 

`this\.` 

Surely this regular expression should match **this.**

## Shortcut advanced

`\s` : matches whitespace, including space, table, line break, etc.

`\S` : opposite of `\s`, anything but whitespace.

`\d` : matches a digit.

`\D` : opposite of `\d`, anything but digit.

`\w` : matches a word character. `[A-Za-z0-9_]`. 

`\W` : opposite of `\w`, anything but a word character.

`\$\d{4}` : starts with $, and followed by 4 digits

Today I learned **\$5832**7 but lost **\$3826**.

## Non printable characters

* **Tab** : `\t`
* **Carriage return** enter : `\r`
* **Line feed (or newline)** : `\n`

## Anchors - ^ and $

`^` : represents the beginning of the line.

`$` : represents the end of the line.

`^\d+` : identify a number but only if it is the very first thing on the line.

**13** cats escaped from the 5 cages at the vet's clinic.

## Word Boundaries

* `\<` : represents the beginning of a word.
* `\>` : represents the end of a word.
* `\b` : represents either the beginning or end of a word.