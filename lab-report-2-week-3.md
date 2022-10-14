# Lab Report 2
## Simpleist Search Engine
---
Here is my code for the Simpleist Search Engine:
```
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;

class Handler implements URLHandler {

    int num = 0;
    ArrayList<String> listRequest = new ArrayList<String>();

    public String handleRequest(URI url) {
        String finalOutput = "";
        if (url.getPath().equals("/")) {
            return String.format("This is the Search Engine Homepage");
        } 
        else if (url.getPath().equals("/add")) {
            String[] parameters = url.getQuery().split("=");
            if (parameters[0].equals("s")) {
                listRequest.add(parameters[1]);
                return String.format("Adding... ", listRequest.get(listRequest.size() - 1 ));
                }   
            }
        else if (url.getPath().equals("/search")) {
            String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    for(String s: listRequest){
                        if(s.contains(parameters[1])){
                            finalOutput = finalOutput + " " + s;
                        }
                    }
                    return finalOutput;
                }
            }
            return String.format("We couldn't quite find what you were looking for.");
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

Homepage:
---
This homepage is the default for the Search Engine. It calls the handleRequest function, which reads the "/" in the search bar and then outputs "This is the Search Engine Homepage".

![Homepage](https://media.discordapp.net/attachments/1023749314587140137/1030321411866230814/unknown.png)


Adding an Element:
---
This code calls the handleRequest method again, except that it reads the "/add" in the url, and goes to the first else-if statement. It creates a String array called parameters that looks through the url to find the query symbol, "?", and then split the url after the = sign. Then, it will check if parameters[0] matches "s", which is an indicator that something should be called. 

Then, after creating an ArrayList called listRequest, the code calls for parameters[1], or the actual element we want to be added, into the listRequest to be stored. 

This function was called three times to add two elements named "radish", and one named "dishes".

Adding element radish:
![Adding Elem 1](https://media.discordapp.net/attachments/1023749314587140137/1030321651834966057/unknown.png) 

Adding element dishes:
![Adding Elem 2](https://media.discordapp.net/attachments/1023749314587140137/1030322835375267891/unknown.png)

After successfully adding the element in the search bar, the page changes from the homepage to a page that says "Adding...". 

Search Query:
---

The search statement, or the last else-if statement, can only be called successfully after other elements have been added in. The code creates a new String Array called parameters, which does the same exact thing as the String Array in the /add function, except is separately regarded. Once again, it will search the url until it finds the query symbol, and then split it after the = symbol, and then check if parameter[0] equals "s". 

Next, I created a for loop that will loop through the elements in listRequest, which contains all the elements that were added in /add, and then check to see if any part of the said element contains the phrase in parameters[1] of the /search url. If it does contain it, then it will be added to a currently empty string called finalOutput, and then after all elements are looped through and accounted for in finalOutput, I return finalOutput.

This time, it will look for 
![Search Query](https://cdn.discordapp.com/attachments/1023749314587140137/1030322927222132796/unknown.png)


