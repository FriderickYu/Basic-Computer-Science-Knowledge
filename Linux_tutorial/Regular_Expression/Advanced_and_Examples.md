# Advanced and Examples

## Grouping

We can group several charcters together in our regular expressions using `()`.

`John (Reginald)? Smith` : Reginald occurs zero or one time.

**John Reginald Smith** is sometime just called **John Smith**.

For example, we would like to find instances of IP addresses. An IP address is a set of 4 numbers, separated by full stops.

`\b(\d{1,3}\\.){3}\d{1,3}\b`

The server has an address of **10.18.0.20** and the printer has an address of **10.18.0.116**.

1. `\b` : indicates either the beginning or the end of word, word boundaries.
2. `(\d{1,3}\.){3}` : handle the first 3 chunks so `\d{1,3}` , indicates we are looking for between 1 and 3 digits and we remember to escape the full stop to remove its' special meaning.

## Back references



