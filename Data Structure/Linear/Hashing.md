***Cause the TC - O(1) but SC - O(n)***
A hash table is generally made of an [[Arrays]] of [[Linked List]] and a hash code function - this hashcode function is used to compute the position in the Array via modulo.

1. First, we compute the hashcode of the provided key - note that two different keys might have the same hashcode (**collisions**), so we may have an infinite number of keys with the same hashcode
2. Next, use the hashcode to compute the position in the Array. Typically this is something like `hash(key) % array_length`. Two different codes could of course map to the same index.
3. At this index there is a [[Linked List]] of both keys and values. Store this item and key in the [[Linked List]] - this is done because there may be collisions.

To avoid collisions, we typically ensure that a HashTable has 50% of it's space free, otherwise it's performance becomes much worse. This means that a Hash Table typically takes up quite a lot of space in the form of sequential memory compared to an [[Arrays]].

### Usage
- Used for dictionaries, frequency counting, maintaining data for quick access by key, etc.
- Real World Applications include Database Indexing, Cryptography, Caches, Symbol Table and Dictionaries.

### Not Usage
- Need to maintain sorted data along with search, insert and delete. We use a *self balancing BST* in these cases.
- When Strings are keys and we need operations like prefix search along with search, insert and delete. We use *Trie* in these cases.
- When we need operations like floor and ceiling along with search, insert and/or delete. We use *Self Balancing BST* in these cases.

![[Pasted image 20250416224046.png]]

### Component of Hashing
- Key - what we are going to search when needed
- Hash Function - converting values to hash digest
- Hash Table - where digest are stored

## Some Key Terms
- ### Collision in Hashing
	When two or more keys have the same hash value. It depends on the size of the algorithm, the distribution of hash values and the efficiency of Hash function.
	we tackle this by **rehashing**.

- ### Load Factor
	Number of items the hash table contains divided by the size of the hash table.
	LF = total_elements / size_of_table. Default is 0.75.
- ### Rehashing
	Hashing again when collision occurs or when **LF** **increases** than set/default value.

## Collision Resolution Techniques
### 1. Separate Chaining
   Make each cell of the hash table **point to a linked list of records** that have the same hash function value. Chaining is simple but **requires additional memory** outside the table
### 2. Open Addressing
   All elements are **stored** in the **hash table itself**. Each table entry contains either a record or NIL. When searching for an element, **we examine** the table slots **one by one** until the desired element is found or it is clear that the element is not in the table.
	### 1. Linear Probing
		    Hash table is **searched sequentially** that starts from the original location of the hash. If in case the location that we get is already occupied, then we check for the next location.
	### 2. Quadratic Probing
			Quadratic probing operates by taking the original hash index and **adding successive values** **of** an arbitrary **quadratic polynomial** until an open slot is found.
				An example sequence using quadratic probing is:
					$H  + 1^2  ,  H  + 2^2  ,  H  + 3^2  ,  H  + 4^2  ………………….  H  + k^2$ 
	### 3. Double Hashing
			It **uses two** Hash Functions. First if no collision. **Second** to be used along with first **when** **collision** occurs.

### Types of Hashing 

1. HashMap
2. TreeMap - // used when we need sorted order inside hashmap
3. HashSet
4. TreeSet -  // used when we need sorted order inside hashset
5. many more like for Thread safety...

### Initialization 
	Map<Data-type, Data-type> map = new HashMap<>(int initialCapacity, float loadFactor); // capacity are optional
	Map<Data-type, Data-type> treeMap = new TreeMap<>(int initialCapacity, float loadFactor);
	Set<Data-type> set = new HashSet<>(int initialCapacity, float loadFactor);
	Set<Data-type> treeSet = new TreeSet<>(int initialCapacity, float loadFactor);

### Insertion/Updating in maps only
	map.put(Key, Value);
	map.put(Key, Value);
	set.add(Key);
	treeSet.add(Key);

### Fetching
	map.get(Key);
>	set doesn't need this method
### Deletion
	map.remove(Key);
	treeMap.remove(Key);
	set.remove(Key);
	treeSet.remove(Key);

	map.clear(); // to delete everything
	set.clear();


### Traversal
#### - Map
	for (Map.Entry<String, Integer> e : map.entrySet())
        System.out.println("Key: "+e.getKey()+" Value: "+e.getValue());
#### - Set
	for (String element : hs)
            System.out.print(element + " , ");

### Searching
	map.containsKey(key);
	map.containsValue(Value);

### Other Useful Methods
	entrySet() // Returns a Set view of the mappings contained in this map.
	keySet() // Returns a Set view of the keys contained in this map.
	size() // Returns the number of key-value mappings in this map.

	getOrDefault(Object key, V defaultValue) // Returns the value to which the specified key is mapped, or defaultValue if this map contains no mapping for the key.
	