Collection of **nodes connected in a tree-like structure** where each node represents a character. Mainly used for storing strings efficiently.

### Usage
- Autocomplete systems
- Spell checkers
- IP routing (Longest prefix match)
- Search engines (prefix matching)
- DNA sequencing

### Characteristics of Trie
- **Root node** is empty (doesn't store any character)
- Each **path** from root to leaf represents a word
- Each node can have **up to 26 children** (for lowercase a-z), or more for extended character sets
- Fast prefix-based retrieval

---

### Trie Node Structure
`class TrieNode {`
    `TrieNode[] children = new TrieNode[26]; // For 26 lowercase English letters`
    `boolean isEndOfWord; // True if node marks the end of a word`
`}`

### Trie Operations

| Operation          | Time Complexity |
| ------------------ | --------------- |
| Insert Word        | O(L)            |
| Search Word        | O(L)            |
| Starts With Prefix | O(L)            |

> Where **L** is the length of the word or prefix

### Implementation of Trie

`class Trie {`
    `private TrieNode root;`

    public Trie() {
        root = new TrieNode();
    }

    // Insert word
    public void insert(String word) {
        TrieNode node = root;
        for (char ch : word.toCharArray()) {
            int i = ch - 'a';
            if (node.children[i] == null) {
                node.children[i] = new TrieNode();
            }
            node = node.children[i];
        }
        node.isEndOfWord = true;
    }

    // Search for full word
    public boolean search(String word) {
        TrieNode node = searchPrefix(word);
        return node != null && node.isEndOfWord;
    }

    // Check if any word starts with this prefix
    public boolean startsWith(String prefix) {
        return searchPrefix(prefix) != null;
    }

    // Helper function to return node at end of prefix
    private TrieNode searchPrefix(String prefix) {
        TrieNode node = root;
        for (char ch : prefix.toCharArray()) {
            int i = ch - 'a';
            if (node.children[i] == null) {
                return null;
            }
            node = node.children[i];
        }
        return node;
    }
`}`

---

### Benefits
- **Fast prefix lookup**: ideal for autocomplete, dictionaries
- Efficient storage for **many words with shared prefixes**
- Better than HashMap for **prefix-based search**

### Downsides
- **High memory usage** if implemented naïvely    
- Not suitable for very large alphabets unless optimized (use `Map` instead of array)

### Optimizations
- Use `Map<Character, TrieNode>` instead of array to reduce space for sparse alphabets
- Use **Compressed Trie** (Radix Tree) to reduce depth    
- Store frequency or weights for recommendation systems