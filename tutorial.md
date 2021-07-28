## JBang in Google Cloud Shell

JBang lets Students, Educators and Professional Developers create, edit and run self-contained source-only Java programs with unprecedented ease. 

This tutorial will show you how to use JBang within Google Cloud Shell.

To get started lets setup JBang in your Google Cloud Shell:

```bash
curl -Ls https://sh.jbang.dev | bash -s - app setup
```

This will install and setup latest version of JBang.

You will only need to do this once as it will update `~/.bashrc` which stays persistent
between Google Cloud Shell sessions.

To check the setup worked you can run `jbang` and see it print its usage help:

```bash
jbang
```

**Tip**: Click the copy button on the side of the code box and paste the command in the Cloud Shell terminal to run it.

Next, you’ll write and launch a basic hello world.

## Hello World with JBang

Now lets create a first JBang script.

```bash
jbang init helloworld.java
```

