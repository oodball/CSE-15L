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
![Homepage]()


Adding an Element:
---
![Adding Elem 1](https://media.discordapp.net/attachments/1023749314587140137/1030321651834966057/unknown.png) 

![Adding Elem 2](https://media.discordapp.net/attachments/1023749314587140137/1030322835375267891/unknown.png)

Search Query:
---
![Search Query](https://cdn.discordapp.com/attachments/1023749314587140137/1030322927222132796/unknown.png)


