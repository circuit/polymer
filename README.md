# Obsolete. Use https://github.com/circuit/circuit-web-components instead

# Circuit Polymer Components compatible with Polymer 0.5

Example polymer components for the Circuit Collaboration Software by Unify.

> For Polymer 1.0 compatible components view the individual repos. 
> E.g. https://github.com/yourcircuit/circuit-api

> To see a list of all Circuit Polymer 1.0 components filter by 'circuit-' 

> https://github.com/yourcircuit/?utf8=%E2%9C%93&query=circuit-

## Prerequisites
To use the SDK you need to get free developer account. Get your developer account today at [https://developers.circuit.com](https://developers.circuit.com).

## Compatibility
Polymer components are supported on any modern browser. Some functionality such as WebRTC is currently limited to Chrome, but IE and FF support is near.

## List of example components

**circuit-api**

[API Documentation](https://rawgit.com/yourcircuit/polymer/master/components/circuit-api/index.html) | [Source code](https://github.com/yourcircuit/polymer/tree/master/components/circuit-api) 

The circuit-api component is a non-UI component that acts as interface to the new leight weight [JS SDK] (JSDoc link to follow). We are trying our best to keep the circuit-api APIs up to date with the JS SDK, but if something is missing you can always add it.


**circuit-chat**

[API Documentation](https://rawgit.com/yourcircuit/polymer/master/components/circuit-chat/index.html) | [Source code](https://github.com/yourcircuit/polymer/tree/master/components/circuit-chat) 

Simple chat module wher you can post messages in a Circuit direct/group conversation and get notified on new messages arriving. Uses session cookie to login if available, otherwise asks for credentials.

[Try it out live](https://rawgit.com/yourcircuit/polymer/master/chat.html)

All that's needed is to import the component and use it with a single line of HTML code.

```html
<link rel="import" href="components/circuit-chat/circuit-chat.html">
<circuit-chat
  auto-logon 
  conversation="ef675fc5-dcb1-4fe2-bcd1-83f32be5466f">
</circuit-chat>
```

... you can also listen to the on-message event in JavaScript
```javascript
document.getElementById('chat').addEventListener('message', function (m) {
   console.log('Message from ' + m.detail.sender + ': ' + m.detail.text);
});
```

## Run these examples locally

 1. Clone this repo
 2. Install node-static via `npm install node-static`
 3. Run the example by navigating to `http://localhost:8080/chat-example.html`

## Develop your own component

 1. Fork this repo
 2. Create your own amazing components 
 3. Include circuit-api to take advantage of the Circuit API
 4. Share them with the rest of us :)

