# SimplePebble
This is a simple guide to build a pebble app for someone who actually knows how to code.

## Dependencies 
  Start by installing pebble bindings.

  ```brew install pebble```


To make sure this is working, run the unsurprising `pebble` command. 

```shell
➜  pebble
usage: pebble [-h] [--version]
              {sdk,build,clean,install,logs,screenshot,insert-pin,delete-pin,emu-accel,emu-app-config,emu-battery,emu-bt-connection,emu-compass,emu-control,emu-tap,emu-time-format,ping,login,logout,repl,transcribe,data-logging,new-project,kill,wipe,analyze-size,convert-project,gdb}
              ...
pebble: error: too few arguments
```

If you get an error like the above, congratulations! It's installed, you're doing great. 

## Setting up for development

So in general, the pebble has a couple of simple build steps. 

You write your application source code, and then you compile it for the pebble, and then push it to the pebble. 
This happens by sending it over wifi to your phone, and then over bluetooth to the pebble. 

In order for your phone to receive apps to send to your pebble, it's very simple. Open the pebble app, scroll to the bottom and hit `Enable Developer Mode`. 

SCREENSHOT HERE

Now, you should be able to see a developer connection screen. If you're not a fan of CloudPebble like me, and you like to see what's actually happening, then this is where you wanna be. 

If you have successfully enabled it, you should see something like, `Listening on 192.168.1.9`.

SCREENSHOT HERE

Now you should be all ready to start sending it some code. 

## Building from Source to the Pebble

Let's start with the sample application. We start by making the sample code, for a project called `yolo`, we'll `cd` into the repo and build it, then install it on our phone 

```shell
pebble new-project yolo
cd yolo
pebble build
pebble install --phone 192.168.1.9
```

And that's it.  Now you can start building on the Pebble with their regular docs for `C`. 

### I can't recommend their guide for C enough. [Check it out](https://developer.pebble.com/tutorials/watchface-tutorial/part1/)

## Troubleshooting

### Make sure when pushing code to the pebble that your phone and laptop are on the same wifi network, you might run into some problems pushing apps to different IP's. If you get a connection timeout, try `ping`ing that address to see if you can send it traffic. 

