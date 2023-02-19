# Introduction - What does regular expression do?

Regular expression, just like filters and wildcards, to create a pattern and filter data. With regular expressions you can:

1. **Search**, like identify all email addresses in some content using a text editor.
2. **Replace**, like clean up some poorly formatted `HTML` by replacing all uppercase tags with lowercase equivalents in a text editor.
3. **Validate**, check whether passwords meets certain criteria, such as a mix of uppercase and lowercase, digital etc.
4. **Coordinate**, wish to process files in a directory, but only if they meet particular conditions.
5. **Reformat**, export data from one program as text file then modify its layout so you may import it into another program using a text editor.

`b[ia]` : match every instance of the character `b` followed by either the character `i` or `a` So if we ran that regular expression over the following text it would match as follows

*The **bat** took a **bite** out of the **big** boring apple.*

