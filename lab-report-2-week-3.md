# Lab Report 2
## Part 1
In week 2, we were assigned to create the simplest "search engine"  that implements a web server that tracks a list of strings. This search engine has the ability to add a new string to a list and returns a list of strings given a specific substring.

**Here is the code for the search engine:**
```java
import java.io.IOException;
import java.net.URI;
import java.util.*;

class Handler implements URLHandler {
    int num = 0;
    List<String> stringList = new ArrayList<String>();

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return String.format("");
        } else if (url.getPath().contains("/add")) {
            String[] parameters = url.getQuery().split("=");
            stringList.add(String.format(parameters[1]));
            return (String.format(parameters[1]) + " added!");
        } else if (url.getPath().contains("/search")) {
            List<String> newList = new ArrayList<String>();
            String[] userSearch = url.getQuery().split("=");
            for (int i = 0; i < stringList.size(); i++) {
                if (String.format(stringList.get(i)).contains(String.format(userSearch[1]))) {
                   newList.add(String.format(stringList.get(i)));
                }
            }
            return (Arrays.toString(newList.toArray()));
        }
        return "";
    }
}

class SearchEngine {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}
```
The next 3 screenshots represent how I added elements to the overrall list that will later be searched for a specific susbtring.
