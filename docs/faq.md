# FAQ

## My OS is not listed under `/download`!
Open a <i>"General Support"</i> ticket on our [Discord Server](index.md).

## "java.lang.UnsatisfiedLinkError [...] libc.so: cannot open shared object" stacktrace.
<b>There are two ways to fix this:</b>

### Custom Docker Image <b>(Recommended if using a Docker-based panel)</b>
We forked the Pterodactyl Docker images and created [our own](https://github.com/Clouds-Studios/Docker-Images) that you can use.<br>
The only difference compared to the default one used by Pterodactyl is a symlink for the C library file <i>(libc.so)</i>, you can check it yourself!

To use it, just paste the desired image URL <i>(found on the page linked above)</i> into your server configuration.

<i>In this example, we'll use the Pterodactyl panel:</i><br>
Let's say I want to use Java 17, so my URL will be `ghcr.io/clouds-studios/yolks:java_17`.<br>
On the server tab, under <i>"Docker Image Configuration"</i>, in the <i>"Or enter a custom image..."</i> field, I'll paste the previously copied URL. <i>([Example Image](https://imgur.com/a/0NktCBA))</i>

### Server Starter Jar
If you don't use a Docker-based panel or don't want to use the custom Docker image, we have another solution, a bit more complex, but still viable.

Just download our [Server Starter.jar](https://bit.ly/cloudsstudiosstarter) and place it in your root folder <i>(the folder containing the main Jar file)</i>, then start it instead of the main server Jar.

If you want to change the command the starter uses to launch the server, you can do so via the config file it generates: `server_starter.yml`.

### Didn't work?
Open a "Bug Report" ticket on our [Discord Server](index.md).