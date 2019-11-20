## Resources:

-   Github sample project
    

## Nativescript: The Cross-Platform Mobile Framework that Could

  

Today I would like to introduce a powerful, but lesser-known mobile development framework called Nativescript.

  

If you are not an Angular developer or you do not have a keen interest in the more obscure cross-platform mobile frameworks, you may never have heard of Nativescript.

  

My goal in this article is to give a brief overview of Nativescript, build a simple hello world app, and show off some of its more prominent features.

### What is Nativescript?

  

In the simplest terms, Nativescript is a cross-platform Javascript/Typescript mobile development framework. Like Titanium, Xamarin and its most direct competitor React Native, Nativescript is trying to solve the problem of building performant mobile applications for android and iOS from a single codebase. Like React Native, Nativescript also allows for the opportunity to further consolidate a project’s codebase by basing its application architecture on modern web frameworks.

  

Where React Native is an extension of React, Nativescript is in fact much more platform agnostic, supporting Angular 2+, Vue.js, and a vanilla Javascript/Typescript integration. This means that, with certain constraints, a Nativescript app can share a majority of its code between the web, android, and iOS implementations. The Angular 2 flavor is by far the most popular and will be the focus of this article.

  

### Why Use Nativescript?

  

In my experience using Nativescript in production, the main reason you would choose it over another cross-platform framework is if you have already chosen one of the web frameworks it supports and want to take advantage of the ability to share a codebase and the benefits of not needing to train engineers to use a new framework. So if you want to build a mobile app and already know Angular 2 or Vue.js, Nativescript is a natural choice.

  

As an Angular developer, I found Nativescript incredibly easy to pick up, and aside from the user interface, found integrating my Angular codebase quite seamless. The vast majority of the cross-platform applications I built were able to share 90% or more of the logic governing things like navigation, communication with the backend, and data binding. For anything that was pure Javascript/Typescript, I was able to share 100% of the code.

  

The main differences came from code related to the user interface. Building the UI will be somewhat different. Nativescript simulates creating views with HTML and CSS but because the views compile down to native UI elements, it does not function exactly the same

  

So if you are familiar with Angular 2 or Vue.js, Nativescript is a natural choice for building a cross-platform mobile application or a mobile extension of your existing web application.

  
  

## Building Our First Project

  

The Angular implementation of Nativescript is the most popular and it is the implementation we will be using for this demonstration. One of the main benefits of using Nativescript Angular is that it gives us access to Angular’s incredible CLI, which will rapidly give us the ability to create an application scaffolding as well as generating our components.

  

### Getting Your Environment Set Up

Getting your environment set up:

For the purpose of this tutorial, we are going to assume your environment includes an up to date version of Node, NPM, and Typescript. We are also assuming that you are developing on an updated version of Mac OS. In my experience, mobile development is always easier on the Mac platform since Apple has such tight restrictions on development for their hardware. Xcode and all other iOS related development tools are significantly easier to use on Mac OS.

  

First, we need to install the Nativescript CLI with the following command:  
  

`npm install -g nativescript`

  

Verify your installation by running tns --version. At the time of writing the most up to date version is 6.2.1

  

Second, set up your environment for mobile development by entering

  

`ruby -e "$(curl -fsSL [https://www.nativescript.org/setup/mac](https://www.nativescript.org/setup/mac))" `

  

Into your terminal.

  
This will walk you through the setup process and install any applications your machine may be missing such as Xcode or Homebrew.

  

### Step 2

  

Building your first Nativescript project.

  

Once you have the CLI set up, type `tns create my-project --ng`

  

The --ng flag at the end indicates to the CLI that you want to build an Angular project and will set up the project scaffolding accordingly.

  
  

Once the CLI has completed set up, enter

  

`tns doctor`

  

into your terminal.

  

‘tns doctor’ is a powerful command that will identify any issues your environment may have. Once you have your first project set up it will be invaluable for making sure all dependencies are installed and up to date. It is also useful for determining if there are any issues with your simulators or SDKs. Whenever I have an issue with my build, this command is always a useful check to determine if the source is outside the application itself.

  

In our case we might come back with the following error: ✖ WARNING: CocoaPods is not installed or is not configured properly.

  

Because we will be building our project with the Preview app, we don’t need to worry about installing Cocoapods yet. Just know that should we try to install the app directly onto an iOS device we will need to do some additional steps. 

  

You also should be able to see a QR code appear in the terminal. If you have Nativescript Preview and Nativescript Playground installed you will be able to scan this QR code and see your app.

  
  

### Installing Preview and Nativescript Playground

  

In order to use this QR code to view your app, you will need to have Nativescript Preview and Nativescript Playground installed.

  

Go to the apple app store or the google play store and install both Nativescript Preview and Nativescript Playground.

  

Once they are installed, run the command

  

`tns preview`

  

In the terminal.

You should see something that looks like this: 

![Alt text](https://i.imgur.com/hl3JURN.png "Optional title")

A QR code will appear. Scan it and Nativescript Preview will open on your phone. In it you should be able to see a live version of your app. Preview also has the handy feature of being able to sync with your phone. When you make updates to your app, it will reload the application on your phone and you will very quickly be able to see the changes.

  

If you scan the QR code and you phone opens Preview and the screen looks something like this:

  ![Alt text](https://i.imgur.com/RKMY21K.jpg "Optional title")
  
  

Congratulations you have built your first Nativescript app!

*Note: since Preview works over your WiFi connection, it can take a while to load if your connection is spotty.*

  

## Wrapping Up

  

### Pros

One great thing about nativescript is the ability to quickly set up and build a project, and then have it appear on your device for testing. The UI is intuitive and performant, and it enforces the opinionated structure of Angular, with all it’s built in features. This means that out of the box you do not need many dependencies or third-party libraries. When you are able to use Preview, it also means that your UI updates lightning fast. So for prototyping and building applications that do not require third-party integrations, Nativescript is an excellent choice. It also has a great of code you can share between your Angular and Nativescript implementation. Between React Native and Nativescript, I found Nativescript to be easier to switch between mobile and web.

  

### Cons

Nativescript has a small support community. This means that not only is it often difficult to find answers to questions you might have, but it also means that there are a fairly small number of third-party libraries out there to use. Because it is based on the Angular Framework, you often have much more you can do before needing to reach for a third-party library, but once you do it can be difficult to find one that meets your needs. In addition, many third-party libraries are unsupported by Preview, meaning you need to build the app through the command line or Xcode/Android Studio. While these solutions are still perfectly fine in most cases, in my experience some libraries caused a significant increase in build time. For example, adding firebase integration sometimes resulted in a built time measured in minutes, rather than seconds.

  
  

## Final Thoughts

I think that Nativescript is a great solution if you need to build a mobile integration for an Angular web app quickly. The speed of execution, the intuitiveness of its design, the cross-platform nature, and the ease of integrating Angular code makes it a compelling choice. However, many of these benefits are lost should you need to build beyond the core Nativescript/Angular framework. My suggestion is to play around with it and decide for yourself. However, I would not invest too heavily in this technology until the issues with third-party integrations are fully worked out.
