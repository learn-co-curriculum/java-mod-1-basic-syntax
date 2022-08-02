# Java Basic Syntax

## Learning Goals

- Explain basic Java Syntax

## The Curly Braces

We have discussed 2 main groupings thus far: the class and the method. We will go more in depth on what a class and 
method are in the upcoming lessons. For now, know that a class is a grouping of methods and a method is a grouping of
instructions. There are many other ways to group instructions in Java, which we will cover later,
but all of these groupings have something in common: they start and stop with curly braces.

Here is an empty class:

```java
public class Sample { 
} 
```

The `public class Sample` keywords are there to define that:

<ol type="a">
    <li> This is a class </li>
    <li> It can be used by anyone (we will explain this in detail later) </li>
    <li> Its name is "Sample" </li>
</ol>

Then the `{` (open curly brace) indicates that the content of the class is to follow, until we include a matching `}`
(close curly brace). Everything between those two curly braces will be considered part of the definition of the class.

### Curly Braces Match

Where there is an open curly brace, there must be a matching close curly brace. However, there can be more than one
curly brace in a row, because groupings can occur inside each other. We have already seen an example of that with our 
`SimpleSample` class:

```java
public class SimpleSample {
    public static void main(String[] args) {
        System.out.println("Hello World"); 
    }
}
```

The `public static void main(String[] args) {` method occurs inside the `SimpleSample` class definition and starts
with its own open curly brace.

This simply means that the `main()` method is inside the `SimpleSample` class. We must be careful to close the `main()`
method before we close the `SimpleSample` class.

## Russian Dolls

One way to understand the matching rules for curly braces is to think about Russian dolls.

Russian dolls are dolls that can be nested inside of one another. A large doll has a cap that opens to reveal a
smaller doll inside it. That smaller doll also has a cap that opens to reveal yet an even smaller
doll inside it. So on and so forth until the smallest doll doesn't open up.

For now, let's consider just three dolls. The first doll, we'll call it `largestDoll`, opens and has a doll inside it.
That second doll, we'll call `mediumDoll`, also opens and has a smaller doll inside it. That third doll, we'll call it
`smallestDoll`, is sealed and does not have a doll inside it.

Now think of the top of each doll as an open curly brace `{` and the bottom of each doll as a close curly brace `}`.
We start with `largestDoll`, closed:

```java
largestDoll {
} 
```

When we open `largestDoll`, we see `mediumDoll`, closed:

```java
largestDoll {
    mediumDoll {
    }  
} 
```

When we open `mediumDoll`, we see `smallestDoll`, closed:

```java
largestDoll {
    mediumDoll {
        smallestDoll { 
        } 
    }  
} 
```

And `smallestDoll` is sealed.

This example allows us to visualize the following:  

1. Each doll needs a top and a bottom, otherwise it wouldn't be a doll. Each grouping needs a `{` and a `}`
2. The top of a smaller doll cannot be matched with the bottom of a bigger doll and vice-versa. The `}` for `smallestDoll`
must match with the `{` from `smallestDoll`, otherwise the nesting does not work.

As you can see from this example, we use formatting to make it easier to match up curly braces. It is convention in `Java`
to always indent the line after the open curly brace `{` so that the "content" inside its grouping is visually separated.

Whereas it is a universal convention to indent content inside curly braces, the exact way in which to do so is hotly contested.
Here are a couple of variations:

Both curly braces on their own line, with the indentation as a tab character:

```java
public class SimpleSample 
{
    public static void main(String[] args) 
    {
        System.out.println("Hello World"); 
    }
}
```

Both curly braces on their own line, with the indentation as two space characters:

```java
public class SimpleSample 
{
  public static void main(String[] args) 
  {
    System.out.println("Hello World"); 
  }
}
```

The open curly brace on the same line as the definition preceding it and the indentation as four spaces - this is
the most common convention and the one we will use in this course:

```java
public class SimpleSample {
    public static void main(String[] args) {
        System.out.println("Hello World"); 
    }
}
```

## The Semicolon

Most instructions in Java end with a `;`. This is a mechanism Java uses to make it easier to format instructions on 
multiple lines. For example, our earlier `println()` instruction was written as follows:

```java
    System.out.println("Hello World"); 
```

But it could also be written like this:

```java
    System.
    out.
    println("Hello broken World"); 
```

This will come in handy when we start writing more complex programs with longer instructions.

Note that curly braces, class definitions (`public class SimpleSample`) and method definitions 
(`public static void main(String[] args)`) are not followed by `;`. As a matter fact, any instruction that is a 
"grouping" is a followed by an open curly brace and therefore does not require a `;`.
