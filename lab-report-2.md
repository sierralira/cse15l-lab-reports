## Lab Report 2: Servers and Bugs
### Part 1: String Server


```
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    
    String string = "";

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return string;
        }
        else {
            System.out.println("Path: " + url.getPath());
            if (url.getPath().contains("/add-message")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    string += parameters[1] + "\n";
                    return string;
                }
            }
            return "404 Not Found!";
        }
    }
}

class StringServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number!")
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}
```
