# Java 8 Features

This repository provides a detailed explanation of Java 8 features such as Lambda Expressions, Method References, Stream API, Functional Interfaces, and more.

---

## Stream API Overview

The **Stream API** was introduced in Java 8 to process collections (like `List`, `Set`) in a functional and efficient way.

---

### Stream Workflow

Streams operate like a pipeline with the following steps:

1. **Create a stream**
2. **Apply intermediate operations** (e.g., `filter`, `map`)
3. **End with a terminal operation** (e.g., `collect`, `forEach`, `count`)

---

### Key Concepts

- **Intermediate operations:** Transform or filter data. They return a stream and are chainable. These operations are lazy—they don’t execute until a terminal operation is called.
- **Terminal operations:** Produce a result or a side-effect, ending the pipeline.

---

## Intermediate vs Terminal Operations

### Intermediate Operations

_Return a stream and can be chained. These are lazy and only execute when a terminal operation is present._

- `filter()` – Includes only elements matching a condition
- `map()` – Transforms each element (e.g., squaring numbers, converting types)
- `flatMap()` – Flattens nested collections into a single stream
- `distinct()` – Removes duplicate elements
- `sorted()` – Sorts elements in natural order
- `sorted(Comparator)` – Sorts using custom logic
- `limit(n)` – Limits the stream to the first n elements
- `skip(n)` – Skips the first n elements
- `peek()` – Used for debugging; inspects elements without consuming the stream

**Note:** Intermediate methods are chainable and lazy.

---

### Terminal Operations

_End the stream pipeline and produce a result._

- `collect()` – Gathers elements into a collection (e.g., `List`, `Set`, `Map`)
- `forEach()` – Performs an action for each element (e.g., printing)
- `count()` – Returns the number of elements
- `reduce()` – Combines elements using an operation (sum, product, etc.) to return a single value
- `toArray()` – Converts stream elements to an array
- `min()`, `max()` – Finds the minimum or maximum element using a comparator
- `anyMatch()` – Returns `true` if any element matches a condition
- `allMatch()` – Returns `true` if all elements match a condition
- `noneMatch()` – Returns `true` if no elements match a condition
- `findFirst()` – Returns the first element (as an `Optional`)
- `findAny()` – Returns any one element (useful in parallel streams)

---

## Example: Stream Usage in Java

```java
import java.util.Arrays;
import java.util.List;

public class StreamExample {
    public static void main(String[] args) {
        List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5, 6, 7, 8, 9, 10);

        // Filter even numbers, square them, and collect to a list
        List<Integer> squaredEvens = numbers.stream()
            .filter(n -> n % 2 == 0)    // Intermediate: keep even numbers
            .map(n -> n * n)            // Intermediate: square each
            .collect(Collectors.toList()); // Terminal: collect results

        System.out.println(squaredEvens); // Output: [4, 16, 36, 64, 100]
    }
}
