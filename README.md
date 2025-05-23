# Java-8-Features
The Stream API was introduced in Java 8. It's used to process collections (like List, Set) in a functional and efficient way.

Stream Workflow
Stream works like a pipeline:
1. Create a stream
2. Apply intermediate operations (like filter, map, etc.)
3. End with a terminal operation (like collect, forEach, count)
In Short:
Intermediate operations are like filters and transformers — they return streams and can be chained. 
Terminal operations are the final steps — they end the chain and return a result (like a value, collection, or perform an action).

Intermediate vs Terminal Operations
1. Intermediate	- Returns a stream again	
filter() – used to include only those elements that match a condition.
map() – transforms each element, like squaring numbers or converting them to strings.
flatMap() – used when elements themselves are collections; it flattens them into a single stream.
distinct() – removes duplicate elements from the stream.
sorted() – sorts elements in natural order.
sorted(Comparator) – sorts using a custom comparison logic.
limit(n) – restricts the stream to the first n elements.
skip(n) – skips the first n elements of the stream.
peek() – mainly used for debugging; allows looking at elements without consuming the stream.

Note : These operations are chainable, meaning you can perform multiple transformations one after the other, 
and  Intermediate methods are lazy — they don’t execute until a terminal method is called.

2. Terminal - Ends the stream pipeline, gives a result	
collect() – gathers the elements into a collection like a List, Set, or Map.
forEach() – performs an action like printing or saving for each element in the stream.
count() – returns the number of elements in the stream.
reduce() – combines all elements using an operation (like sum or product) and returns a single value.
toArray() – converts the stream elements into an array.
min() and max() – find the minimum or maximum element using a comparator.
anyMatch() – returns true if any element matches a given condition.
allMatch() – returns true if all elements match a condition.
noneMatch() – returns true if no element matches the condition.
findFirst() – returns the first element in the stream (as an Optional).
findAny() – returns any one element, useful for parallel streams.
