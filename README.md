# Boolean primitive getter issue

To reproduce simply run
```shell
./gradlew clean build -x test
```

and check the generated [file](build/generated/sources/dgs-codegen/com/example/demo/types): `Test.java`


From the graphql Schema:

```graphql
type Test {
    primitive: Boolean!
    boxed: Boolean
}
```

This is the generated code:
```java

public class Test {
  private boolean primitive;

  private Boolean boxed;
  
  [...]

  public boolean getPrimitive() {
    return primitive;
  }

  public void setPrimitive(boolean primitive) {
    this.primitive = primitive;
  }

  public Boolean getBoxed() {
    return boxed;
  }

  public void setBoxed(Boolean boxed) {
    this.boxed = boxed;
  }
  [...]
}

```

