###  consider static factory methods over constructors
* A class can provide a **public static factory method**, which returns an instance of the class.

    public static Boolean valueOf(Boolean b) {
    return b ? Boolean.TRUE : Boolean.FALSE;
    }

 * A class can provide its client with static factory method instead of, or in addition to, public constructors. 

**Advantage**

* Unlike constructors **they have names**
  * static factory with a well-chosen name is easier to use and resulting client code easier to read.
  *  In cases where a class require multiple constructors with the same signature, replace them with static factory methods and carefully chosen names to highlight the difference. 
  * **Not required to create new object** each time they are invoked
  *  This allows immutable classes to use preconstructed instances, or to cache instances as they are constructed and dispense them repeatedly to avoid duplicates..
  *  Boolean.valueOf(boolean) illustrates this technique.
  *  Similar to **Flyweight pattern**, greatly **improve the performance** if equivalent objects are requested often, especially when they are expensive to create.
  * Classes that maintain strict control over instances exists at any time are said to be **instance-control** classes. It allows a class to *guarantee that it is a singleton or noninstantiable*.
  * This is the basis of Flyweight pattern, **Enum types** provide this guarantee.
