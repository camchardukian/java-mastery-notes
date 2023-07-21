# Types

There are two categories of types in Java: _primitive_ and _reference_.

Primitive types are for storing simple values, while reference types are for storing complex objects.

## Primitive Types

### Integer

There are several kinds of primitive types for integers in Java:

- **byte** - 8 bits, used for integers from -128 to 127.
- **short** - 16 bits, used for integers from -32,768 to 32,767.
- **int** - 32 bits, used for integers from -2,147,483,648 to 2,147,483,647.
- **long** - 64 bits, used for integers from -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807.

### Floating Point

- **float** - 32 bits, used for floating numbers.
- **double** - 64 bits, used for floating numbers.

### Other

- **char** - 16 bits, used for all Unicode characters.
- **boolean** - ~1bit (roughly 1 bit), used for booleans.

## Reference Types

In Java the reference types are:

- **Class**
- **Array**
- **Annotations**
- **Interface**
- **Enumeration**

## Strings

Strings in Java are reference types (Classes to be exact).

In Java strings are immutable. Any methods that modify strings will return a new string object.

## Arrays

In Java, arrays have a fixed length. We cannot add or remove items from an array.

If we need to add or remove items, we should instead use a collection class such as a `LinkedList`, `TreeSet`, `HashMap`, etc.

In general, however, arrays in Java are great for being efficient, simple, offering type safety, and being easy to make multidimensional.
