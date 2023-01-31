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

In order to build and run this server on my local computer, I used the terminal commands `javac Server.java StringServer.java` and `java StringServer 4000`. The message `Server Started! Visit http://localhost:4000 to visit.` prompted me to the link [http://localhost:4000](http://localhost:4000) where I was able to use the `add-message` request.  


In order for this to occur, the main method of `String Server` built the server that ran on the speific port, 4000, which was given in the terminal commands by calling on the `start` method of the `Server` class in Server.java. The `start` method took in the values `4000` for the port and `new Handler()` to build the server. 

In my first example, I added `add-message?s=Hello World!` to the URL to get [http://localhost:4000/add-message?s=Hello%20World!](http://localhost:4000/add-message?s=Hello%20World!). This produced the following result: 
>![Image](lab-report-2-image-1.png)

In order for this to occur, the value of `http://localhost:4000/add-message?s=Hello%20World!` was taken in to the `handleRequst` method. `url.getPath()` was called and since the path did not equal `/` the if statment was skipped and the else block began. Within the else block, the statment ` if (url.getPath().contains("/add-message"))` returned true becuase the url value was `http://localhost:4000/add-message?s=Hello%20World!` and thus did contain `/add-message`. The array `parameters` was then set equal to the parts of the query `{"s", "Hello World!"}`, using `url.getQuery().split("=")`. 

Then, the first element of the array `parameters` is checked for its equlity to the string `"s"`. Since the statment `parameters[0].equals("s")` returned true, the value of string, which is the string that is displayed on the page, is set equal to the previous value of string, in this case the string's previous value was empty, with the addition of the value of
`parameters[1]`, in this case being `"Hello World!"`, and `/n`, so the next time this sequence occurs the value of `parameters[1]` will print on the next line. 

Finally, the value of string is returned, dispalying the value of string on the page. Hence, the value of the feilds, 'string', of the class changed.

In my second example, I added `add-message?s=Goodbye World!` to the URL to get [http://localhost:4000/add-message?s=Goodbye%20World!](http://localhost:4000/add-message?s=Goodbye%20World!). This produced the following result:  
>![Image](lab-report-2-image-2.png)

In order for this to occur, the value of `http://localhost:4000/add-message?s=Goodbye%20World!` was taken in to the `handleRequst` method. `url.getPath()` was called and since the path did not equal `/` the if statment was skipped and the else block began. Within the else block, the statment ` if (url.getPath().contains("/add-message"))` returned true becuase the url value was `http://localhost:4000/add-message?s=Hello%20World!` and thus did contain `/add-message'. The array `parameters` was then set equal to the parts of the query, `{"s", "Goodbye World!"}`, using `url.getQuery().split("=")`. 

Then, the first element of the array `parameters` is checked for its equlity to the string `"s"`. Since the statment `parameters[0].equals("s")` returned true, the value of string is set equal to the previous value of string, in this case the value of the string was "Hello World!\n", with the addition of the value of
`parameters[1]`, in this case being `"Hello World!"`, and `/n`.

Finally, the value of string is returned, dispalying the value of string on the page. Hence, the value of the feilds, 'string', of the class changed.

### Part 2: Bugs
The buggy program I will be dicussing is the `reversed` method in ArrayExample.java provided in the lab3 rep

### Part 3: Something I learned
During lab 2, I learned that it is possible to affect what other users see on a server page when connected to the same server and on the same port. For example, my lab partner worked on the ieng6computer `ieng2-203` and on port `7063` and when I visited [http://ieng6-203.ucsd.edu:7063](http://ieng6-203.ucsd.edu:7063) I was able to see the changes he had made to the dispalyed int as well as the string that displayed on the page, which included his name. This new knowledge helped me to understand the possible uses of we servers and the ability for collaboration that they allow. 
