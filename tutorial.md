## JBang in Google Cloud Shell

JBang lets Students, Educators and Professional Developers create, edit and run self-contained source-only Java programs with unprecedented ease. 

This tutorial will show you how to use JBang within Google Cloud Shell.

To get started click the "Start" button in lower right.

## Setup JBang

Lets setup JBang in your Google Cloud Shell.

Enter the following in the shell:

```bash
curl -Ls https://sh.jbang.dev | bash -s - app setup
source ~/.bashrc
```

This will install latest version of JBang.

**Tip**: You will only need to do this once as it will update and source `~/.bashrc` which stays persistent between Google Cloud Shell sessions.

To check the setup worked you can run `jbang` and see it print its usage help:

```bash
jbang
```

**Tip**: Click the copy button on the side of the code box and paste the command in the Cloud Shell terminal to run it.

Next, you’ll write and launch a basic hello world.

## Hello World with JBang

To get started we will let JBang create a java file.

```bash
jbang init helloworld.java
```

When created you can immediatly run it:

```bash
./helloworld.java
```

It should simply print out `Hello World`.

Next you will edit the file to change this message.

## Edit file

In Google Cloud Shell if you are editing singular files you can simply use the command `edit` like this:

```bash
edit helloworld.java
```

First time you open a Java class the editor will just syntax highlight the text. After some seconds you will also be able to have basic content assist.

Try edit the code to have it print some additional text, i.e. print out the arguments.

Next will show you one way of doing that.

## Saying more

One way of changing the source to print arguments is to replace the "System.out" line with this:

```java
out.println("Hello " + String.join(" ", args));
```

Now when running the script it should print out all arguments.

Try it now:

```bash
./helloworld.java JBang in Cloud Shell
```

Congratulations you've now created, run and edited your first Java script using JBang.

Next will show how to use 3rd party dependencies to do more interesting ting with JBang.

## Dependencies

JBang can fetch dependencies from any maven compatible repository. JBang allows you to put those dependencies inside the `.java` files as a comment. An example of such dependency looks like:

```
//DEPS info.picocli:picocli:4.5.0
```

This is telling JBang to fetch the picocli library version 4.5.0 - when nothing else specified it will default to fetch it from Maven central.

We can use JBang to create a full example using the picocli dependendency:

```bash
jbang init -t cli hey.java
```

This will create a file named `hey.java` that <walkthrough-editor-select-regex filePath="hey.java" regex="//DEPS.*">declare a dependency on picocli</walkthrough-editor-select-regex> and <walkthrough-editor-select-regex filePath="hey.java" regex="@Parameters">uses it in code</walkthrough-editor-select-regex>.

You can run it directly using `./hey.java` or use `jbang`. For example to see picocli in action pass in `--help`:

```bash
jbang hey.java --help
```

This will print out the usage instructions for the small utility you just made here

Play around with the code and see what you can make.

**Info**: You will notice the red squiggly lines under annotations and some dependencies. This is an unfortunate limitation of Cloud Shell Editor - it does not enable full Java support; but you can build and run Java just fine.

Next, we'll show how to run a full java server side application.

## A Java server application

To end this tutorial we'll show how to do a full Java server application using Quarkus.

First, lets use JBang to create a Quarkus rest application:

```bash
jbang init -t qrest restapp.java
```

To run it use the following line to run it in so called devmode using at the time of writing latest Quarkus release:

```bash
jbang -Dquarkus.dev -Dquarkus.version=2.1.0.CR1 restapp.java
```

This will build and run Quarkus app. 

You can use the "web Preview" feature in Cloud Shell Editor to open the example on `/hello`.

You can even make changes in <walkthrough-editor-open-file filePath="restapp.java">`restapp.java`</walkthrough-editor-open-file> and when you reload the "web Preview" it should pick up the changes.

# Conclusion

That ends this quick tutorial on using JBang with Google Cloud Shell.

Hope you enjoyed it!

See more about JBang at https://jbang.dev.








