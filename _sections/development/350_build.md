---
title: Build Tools
---

There's app code, then there's code that helps us write the code. Some languages are compiled, but many interpreted (not compiled) languages are still not run directly from your source code. These build tools handle all kinds of grunt work to help us work faster and handle the needs of different environments. 

### Key Concepts

 * _Environment Config:_ The build process can adapt the code for different environments, such as which database you connect to or many other things.
 * _Transpiling:_ In Javascript, code is often not written in Javascript. It is written in Typescript, JSX, CoffeeScript, or some other variant. Transpiling translates the source code to vanilla Javascript. This allows you to write code in a preferred language, but still have the code run in environments (like web browsers) that only support certain languages/versions.
 * _Source maps:_ Transpiled code can be hard to debug, since you wrote it in one style, but it gets run in another - and this throws off line number references for errors. Source maps basically provide for friendly error messages to show you where in the original source the error originated - as opposed to where in the transpiled code the error materialized. 
 * _Minification:_ Frontend in-browser apps are typically minified. This is the process of basically compressing the code to get rid of white space, long variable names, etc. It makes the code fairly unreadable to humans, but quicker to download for the browser. 
 * _Tree shaking:_ You may load lots of libraries, but only use small bits of each. Tree shaking is a process to prune the codebase to only what you are using so that less is sent to the browser, and less has to be dealt with by the machine running it. 


### The STSI Way

 * __Convention__: Unless there is a great reason otherwise, stick to the dominant convention of the framework you use. For example, React.js apps tend to use webpack and babel. Better yet, use react-scripts/create-react-app in that case.
 
