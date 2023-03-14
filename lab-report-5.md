# Lab Report 5
> Written by Hou Wai Wan for CSE 15L Winter 2023

> Go back and pick a favorite lab report or a lab activity you really liked or did not finish. 
> Write a post going into detail on how you did the task, doing the task in a different way, or applying something you learned later to the same task. 

### I will be choosing Lab 2 for this report, and write about how I completed the task of building and running a server locally.

To accomplish the task of building and running a simple server that takes in a request and gives a response, I first had to download the java files required to make
my local machine a server. From my previous knowledge of the client-server model, I will be running a server that "listens" to request on a specific port, in this case
port 4000. While in more complex applications, a client would be another computer sending requests over the internt to this server, in this case my computer 
will also act as the client, sending request to my locally hosted server.

I ultilized the "wavelet" repo made available to us on github and downloaded two key files, **Server.java** and **NumberServer.java**.
> <ins>Server.java</ins> acts as out primary Server class and ultilized Java's built-in HttpServer API. It allows us to create a server that listens to HTTP request on a port.
> It defines an interface called "URLHandler" which has one method, "handleRequest", that takes a URI as an argument and returns a string. The Server 
> class provides a static method "start" which takes two arguments, an integer port and a URLHandler instance. It starts the server and prints a message to the console.

``` 
public static void start(int port, URLHandler handler) throws IOException {
        HttpServer server = HttpServer.create(new InetSocketAddress(port), 0);

        //create request entrypoint
        server.createContext("/", new ServerHttpHandler(handler));

        //start the server
        server.start();
        System.out.println("Server Started! Visit http://localhost:" + port + " to visit.");
    }
```

> <ins>NumberServer.java</ins> is the program with the main method that handles http request using the "URLHandler" interface and starts the server on a specified port
> from the command line argument. The "handleRequest" method takes in various path variables and changes the instance variable integer "num" returned to the output.

```
public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return String.format("Number: %d", num);
        } else if (url.getPath().equals("/increment")) {
            num += 1;
            return String.format("Number incremented!");
        } else {
            System.out.println("Path: " + url.getPath());
            if (url.getPath().contains("/add")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("count")) {
                    num += Integer.parseInt(parameters[1]);
                    return String.format("Number increased by %s! It's now %d", parameters[1], num);
                }
            }
            return "404 Not Found!";
        }
    }
```

To run the two files locally, you first have to compile the two files using the javac command in the following format, <ins>javac Server.java NumberServer.java</ins>.
Then you have to run the java class files with the command line argument as the specified port number, in this we will be using port 4000, <ins>java NumberServer 4000</ins>.
If this is all completed correctly, the message "Server Started! Visit http://localhost:4000" should be printed onto the console. 

This in essence was how I went about completing the task of building and running a simple java web server locally. While not as complex as many of the activites we did in 
labs later on in the quarter, I found this lab to be the most funa s it introoduced me to the concept of a request-response relationship shared between client 
and the server. This is a key concept in Software Engineering today and is the fundamental principle behind how we ultilize large scale web applications over the internet.
