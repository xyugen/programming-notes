## Basic Patterns

- `.`: Matches any character except a newline.
- `^`: Matches the start of a string.
- `$`: Matches the end of a string.
- `\d`: Matches a digit (0-9).
- `\w`: Matches a word character (a-z, A-Z, 0-9, _).
- `\s`: Matches a whitespace character (space, tab, newline).
- `[]`: Character class - matches any character inside brackets.
- `[^]`: Negated character class - matches any character NOT inside brackets.

## Quantifiers

- `*`: Matches the preceding element zero or more times.
- `+`: Matches the preceding element one or more times.
- `?`: Matches the preceding element zero or one time.
- `{n}`: Matches the preceding element exactly n times.
- `{n,}`: Matches the preceding element n or more times.
- `{n,m}`: Matches the preceding element between n and m times.

## Special Characters

- `\`: Escapes a special character.
- `|`: Alternation - matches either the expression before or after it.
- `()`: Grouping - captures and remembers matched content.
- `(?=...)`: Positive lookahead - asserts that a pattern can be found ahead.
- `(?!...)`: Negative lookahead - asserts that a pattern cannot be found ahead.

## Examples

- `/a.b/`: Matches "a", any character, and then "b" (e.g., "aab", "acb").
- `/^start/`: Matches "start" at the beginning of a string.
- `/end$/`: Matches "end" at the end of a string.
- `/[aeiou]/`: Matches any vowel character.
- `/[^0-9]/`: Matches any non-digit character.
- `/x*/`: Matches zero or more occurrences of "x".
- `/x+/`: Matches one or more occurrences of "x".
- `/x?y/`: Matches an optional "x" followed by "y".
- `/\d{3}/`: Matches three consecutive digits (e.g., "123", "456").
- `/word\b/`: Matches "word" as a whole word.
- `/foo|bar/`: Matches either "foo" or "bar".
- `/(foo|bar)baz/`: Matches "foobaz" or "barbaz".
- `/look(?=ahead)/`: Matches "look" only if followed by "ahead".
- `/no(?!t)/`: Matches "no" only if not followed by "t".

## Real-life use cases

1. **Form Validation**: RegEx is commonly used to validate input fields like email addresses, phone numbers, and passwords.
```js
// Email validation
const emailPattern = /^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/;
const isValidEmail = emailPattern.test(inputEmail);
```
    
2. **Data Extraction**: RegEx can be used to extract specific data from a text document, such as dates, URLs, and references.
```python
# Extract dates from a text
import re
date_pattern = r'\d{2}-\d{2}-\d{4}'
dates = re.findall(date_pattern, text)
```
    
3. **Search and Replace**: RegEx is powerful for finding and replacing patterns within a string.
```java
// Replace all occurrences of a word
String newText = text.replaceAll("\\bold\\b", "new");
```
    
4. **URL Validation**: RegEx can help validate URLs in strings or input fields.
```python
# URL validation
url_pattern = r'https?://\S+'
is_valid_url = re.match(url_pattern, input_url)
```
    
5. **Tokenization**: RegEx can help split sentences or paragraphs into words or tokens.
```ruby
# Tokenize text into words
text = "Hello, world! This is a sentence."
tokens = text.scan(/\w+/)
```
    
6. **Log Parsing**: RegEx can be used to parse log files and extract relevant information.
```bash
# Extract IP addresses from a log file
grep -oE "\b(?:[0-9]{1,3}\.){3}[0-9]{1,3}\b" logfile.txt
```
    
7. **Data Cleaning**: RegEx is useful for removing unwanted characters or formatting inconsistencies.
```python
# Remove non-alphanumeric characters
import re
clean_text = re.sub(r'[^a-zA-Z0-9\s]', '', dirty_text)
```
    
8. **HTML Parsing**: RegEx can assist in parsing HTML tags and extracting content.
```js
// Extract content from HTML tags
const html = '<p>Hello <strong>world</strong></p>';
const content = html.replace(/<[^>]*>/g, '');
```
    
9. **Phone Number Formatting**: RegEx can help format phone numbers consistently.
```php
// Format phone numbers
$input = "1234567890";
$formatted = preg_replace('/(\d{3})(\d{3})(\d{4})/', '($1) $2-$3', $input);
```

10. **Parsing CSV**: RegEx can help parse and extract data from CSV files.
```python
# Parse CSV using RegEx
import re
csv_data = "John,Doe,30\nJane,Smith,25"
rows = re.findall(r'([^,\n]+)', csv_data)
```