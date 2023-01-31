## Lab Report 2: Servers and Bugs
### Part 1: String Server
The web server, `StringServer`, is meant to take in a string through a request, in the form of `add-message?s=<string>`, and store the incoming requests in a signle string, which is displayed on the page. In my writing of the web server, `StringServer`, I implmemented the URLHandler interface within Server.java and referenced `NumberServer`, both provided in   the wavelet repository of the Week 2 Lab at [https://github.com/ucsd-cse15l-f22/wavelet](https://github.com/ucsd-cse15l-f22/wavelet). 


Using these resource, I wrote the following code for `StringServer`:
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

In order to build and run this server on my local computer, I used the terminal commands `javac Server.java StringServer.java` and `java StringServer 4000`. The message `Server Started! Visit http://localhost:6000 to visit.`prompted me to the link [http://localhost:4000](http://localhost:4000). where I was able to use the `add-message` request. 

In 
