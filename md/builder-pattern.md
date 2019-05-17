# The Builder Pattern

-

The builder pattern is a design patter for building complex objects

The builder pattern is used to separate the construction of an object from its representaiton

-

Consider the following Java class for an element on the periodic table

```java
public class Element {

    private String name;
    private String appearance;
    private double atomic_Mass;
    private double boil;
    private String category;
    private String color;
    private double density;
    private String discovered_By;
    private double melt;
    private double molar_heat;
    private String named_By;
    private int number;
    private int period;
    private String phase;
    private String source;
    private String spectral_img;
    private String summary;
    private String symbol;
    private int xpos;
    private int ypos;
    private Integer[] shells;

}
```

-

A constuctor for this class might look something like

```java
    public Element(String name, String appearance, 
        double atomic_Mass, double boil, String category, 
        String color, double density, String discovered_By, 
        double melt, double molar_heat, String named_By, 
        int number, int period, String phase, String source,
        String spectral_img, String summary, String symbol, 
        int xpos, int ypos, Integer[] shells) {
            // code to set each field goes here
        }
```

-

This constructor does not spark joy

```java
        element = new Element(
                "Hydrogen",
                "colorless gas",
                1.008,
                20.271,
                "diatomic nonmetal",
                "colorless",
                0.08988,
                "Henry Cavendish",
                13.99,
                28.836,
                "Antoine Lavoisier",
                1,
                1,
                "Gas",
                "https://en.wikipedia.org/wiki/Hydrogen",
                "https://en.wikipedia.org/wiki/File:Hydrogen_Spectra.jpg",
                "Hydrogen is a chemical element with chemical symbol H and atomic number 1. With an atomic weight of 1.00794 u, hydrogen is the lightest element on the periodic table. Its monatomic form (H) is the most abundant chemical substance in the Universe, constituting roughly 75% of all baryonic mass.",
                "H",
                1,
                1,
                new ArrayList<Integer>() {{add(1);}}
        );
```

The fields aren't intuitive here and it would likely be easy to mix up numbers

-

Instead let's create a class to build an element piece by piece.

```java
public class ElementBuilder {
    private Element element;

    public ElementBuilder() {
        element = new Element();
    }
}
```

-

Now we add methods to set each field. This will be our name function

```java
    public ElementBuilder name(String name) {
        this.element.setName(name)
        return this;
    }
```

Notice that the return type of this method is ElementBuilder and we end it with `return this`

-

We can do this for each field. From there we need to create a terminal operator that returns our newly built element

```java 
    public Element build() {
        return element;
    }
```

This function will be the final operation and calling it will indicate that you are done initializing a varibale.

-

We can now use our pattern

```java
public class Main {

    public static void main(String[] args) {
        ElementBuilder e = new ElementBuilder();
        
        e.name("Hydrogen");
        
        e.appearance("colorless gas");
        
        Element element = e.build();
    }
}
```

-

This will generate an element with the name `Hydrogen` and the appearance `colorless gas`

This code however still isn't that nice looking and is very verbose. On top of that we are introducing new variables to our scope. We can actually condence some of this down using the builder return types.

```java
        Element element = new ElementBuilder().name("Hydrogen")
                                .appearance("colorless gas")
                                .build();
```

-

Notice how we can chain the methods together without putting them on separate lines. This is because each methods in a builder class returns itself, so every method can simply have another method chained to it. We can continue to chain methods until we call a terminal operation such as our build function. 

-

### Pros of the builder pattern

* Makes code more readable when generating objects
* Methods can be chained making code simpler and shorter
* Objects can be built dynamically using as many or as few fields as you want
* Fewer constructors need to be created within a class making code cleaner

-

### Cons of the builder pattern

* Need for a builder class architecture is more complex
* Builder classes need to be mutable
* Mutating methods in builders have return types
* Constructed object aren't guarenteed to have set fields

-

<img src="https://duckofminerva.com/wp-content/uploads/2013/01/cute-duck.jpg">