Because we need to process words also

### Ways of Creating a Java String
1. String literal (Static Memory) - **memory efficient**
		``<String_Type> <string_variable> = “<sequence_of_string>”;
2. Using new keyword (Heap Memory)
		`String s = new String(“Welcome”);`
3. By Joining character array
		`String(char[] char_array, int start_index, int count)`

### Types of Strings
1. String - immutable 
2. StringBuffer - mutable and synchronize
3. StringBuilder - mutuable

### Some theories
 when strings are created like this
	String str1 = “Hello”;
	String str2 = “Hello”;
then changing one string will do the change in all of the same strings cause every variable is pointing to the same string in the memory

But when created like this
	String str1 = new String(“Hello”);
	String str2 = new String(“Hello”);
then here both strings are different and point to different strings in memory

### Some Important methods
- `string.length()` return length of string
- `s.charAt(int position)` return character at position
- `s.substring(int start, int end)` return string from start to end, end is optional if we want the whole string from start position.
- `s1.concat(s2)` return string combining s1 and s2, returns NPE if can't do concatination
- `s.indexOf('char character', int start)` returns position of first char from start position, start is optional if we want to search the whole string
- `s.lastIndexOf(char character, int end)` return last index of character from end to very first character, returns -1 if not found
- `s1.equals(s2)` returns true if both s1 and s2 are same object and not same string (mind it)
- `s1.equalsIgnoreCase(s2)` same as above just ignore the upper/lower case
- `s1.compareTo(s2)` compare lexicographically (in sorted order), it will return 0 if equal, -1 if s1 is smaller, 1 if s1 is greater
- `s1.toLowerCase()` converts the s1 to lower case characters
- `s1.toUpperCase()` converts the s1 to upper case characters
- `s1.trim()` removes leading and trailing spaces from string
- `s.replace(char oldCharacter, char newCharacter)` returns the string with the changes
- `s.replace(String oldString, String newString)` returns the string with the changes
- `s.replaceAll(char oldCharacter, char newCharacter)` return the string with all the occurrences replaced
- `s.replaceAll(String oldString, String newString)` returns the string with the changes
- `s.contains("searching string")` returns true if found
- `s.toCharArray()` converts string to character array, very useful in many cases
- `s.startsWith(String suffix, int position)` returns true if string s starts with suffix from the position provided in the parameter, position is optional
- `s.endsWith(String suffix, int position)` same as above but from the end
- `s.split(regex)` regex can be whatever pattern we want to split the string into, like white spaces, any character
- `s.join(CharSequence delimiter, CharSequence... ele)` delimiter string which will be placed while joining the char sequences, like comma(,)