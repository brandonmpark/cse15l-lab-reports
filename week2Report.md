# Week 3 Lab Report

## Part 1

The code I wrote for StringServer is as follows:
```java
class StringHandler implements URLHandler {
    String str = "";

    public String handleRequest(URI url) {
        if (url.getPath().equals("/add-message")) {
            String[] parameters = url.getQuery().split("=");
            if (parameters[0].equals("s")) {
                str += "\n" + parameters[1];
                return str;
            }
        }
        return str;
    }
}

public class StringServer {
    public static void main(String[] args) throws IOException {
        if (args.length == 0) {
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new StringHandler());
    }
}
```

![Add Message Screenshot](https://user-images.githubusercontent.com/25190789/214684356-9641cd71-51df-4f4e-b0b5-54fbbffa4035.png)

After starting the server by compiling and running the main method with some port as a command line argument (3000 for me), I was able to access my server at [http://localhost:3000/](http://localhost:3000/). For the first usage of `/add-message`, the url (http://localhost:3000/add-message?s=hello)[http://localhost:3000/add-message?s=hello] was passed to the `handleRequest` method in `StringHandler`. Since `getPath` returns `"add-message"` for this url, the method then checks the query parameters, which are again valid (in the form `"s=[string]"`). Then, it concatenates the 2nd parameter onto the string `str`. In any case, it finally returns `str`, which is displayed on the page.


![Add Message Screenshot](https://user-images.githubusercontent.com/25190789/214684602-774e1ddc-b69b-4a71-bde5-ec0547329aad.png)

The behavior in the 2nd case is exactly the same as the 1st, except for calling `handleRequest` with a url of (http://localhost:3000/add-message?s=hi)[http://localhost:3000/add-message?s=hi]. Thus, it concatenates a new line `"\n"` and the parameter onto `str`, leading to the observable returned result of `hello` and `hi` separated in different lines.

## Part 2

For the `LinkedList` program, one of my tests was the following:
```java
LinkedList list;
LinkedList emptyList;

@Before
public void setUp() {
    list = new LinkedList();
    list.append(1);
    list.append(2);
    list.append(3);

    emptyList = new LinkedList()
}

@Test
public void testFirst() {
    assertEquals(1, list.first());
    assertThrows(NoSuchElementException.class, () -> emptyList.first());
}
```

![Test Failure Screenshot](https://user-images.githubusercontent.com/25190789/214686573-6930139b-dbb2-45c1-81eb-875ae0b0fddc.png)

The program failed this test, resulting in a `NullPointerException` rather than throwing a `NoSuchElementException` as desired, much like the `last` method does. However, the nonnull input in the test resulted in a success, as the program correctly returned `1` as expected. 


## Part 3
