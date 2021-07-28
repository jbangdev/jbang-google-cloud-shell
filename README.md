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

TO BE CONTINUED soon :)
