# Circuit Polymer Components

Example polymer components for the Circuit Collaboration Software by Unify.

> Components are still based on Polymer 0.5. We are working hard to upgrade them to 1.0.

## Prerequisites
To use the SDK you need to get free developer account. Get your developer account today at https://www.yourcircuit.com/web/developers/home.

## Compatibility
Polymer components are supported on any modern browser. Some functionality with as WebRTC is currently limited to Chrome, but IE and FF as on the way. See [Polymer Compatibility](https://www.polymer-project.org/0.5/resources/compatibility.html) for more info.

## List of example components

**circuit-conf-button**

[API Documentation](https://rawgit.com/yourcircuit/polymer/master/components/circuit-conf-button/index.html) | [Source code](https://github.com/yourcircuit/polymer/tree/master/components/circuit-conf-button) 

Shows a button to start/join a Circuit voice/video/screenshare conference using WebRTC. Uses a polymer paper-dialog component to ask for credentials unless a session cookie is available.

**circuit-call-button**

[API Documentation](https://rawgit.com/yourcircuit/polymer/master/components/circuit-call-button/index.html) | [Source code](https://github.com/yourcircuit/polymer/tree/master/components/circuit-call-button) 

Shows a button to start Circuit voice call using WebRTC. Call can be upgraded to video and screenshare by either party.

**circuit-call-stage**

[API Documentation](https://rawgit.com/yourcircuit/polymer/master/components/circuit-call-stage/index.html) | [Source code](https://github.com/yourcircuit/polymer/tree/master/components/circuit-call-stage) 

UI Component representing the call stage. Shows participants video (or screenshare) as well as active speaker. Supports muting calls, toggle video, etc. Used by circuit-conf-button.

**circuit-jsapi**

[API Documentation](https://rawgit.com/yourcircuit/polymer/master/components/circuit-jsapi/index.html) | [Source code](https://github.com/yourcircuit/polymer/tree/master/components/circuit-jsapi) 

The circuit-jsapi component is a non-UI component that acts as interface to the regular [JS client API](https://circuitsandbox.net/sdk/). At this time the APIs and events are still very limited, but you are welcome to enhance with APIs exposed via the JS Client API.

## Using circuit-conf-button
The [circuit-conf-button](https://github.com/yourcircuit/polymer/tree/master/components/circuit-conf-button) example shows a button with which a user can start/join a WebRTC voice/video/screenshare conference. 

[Try it out live](https://rawgit.com/yourcircuit/polymer/master/conference.html) if you have an account.

All that's needed is to import the component and use it with a single line of HTML code.

```html
<link rel="import" href="components/circuit-conf-button/circuit-conf-button.html">
<circuit-conf-button convId="ca6c5dba-e905-4533-ba71-2c91392a9e47"></circuit-conf-button>
```

As shown in the [API documentation](https://rawgit.com/yourcircuit/polymer/master/components/circuit-conf-button/index.html), the component exposes regular DOM methods and events that can be used.

```html
<link rel="import" href="components/circuit-conf-button/circuit-conf-button.html">
<circuit-conf-button
	convId="ca6c5dba-e905-4533-ba71-2c91392a9e47"
	domain="circuitsandbox.net"
	on-conference-started="{{onConfStarted}}"
	on-user-joined="{{onUserJoined}}"
	>
</circuit-conf-button>
```

... or use them in JavaScript
```javascript
conf = document.querySelector('circuit-conf-button');

// Listen to user-logged-on event
conf.addEventListener('on-circuit-user-logged-on', function () {
	document.querySelector('#me').textContent = conf.localUser.displayName;
});

// Call startConference method on component
conf.startConference({audio: true, video: false}, function () {
	console.log('conference call started');
});
```

## Run these examples locally

 1. Clone this repo
 2. Install node-static via `npm install node-static`
 3. Run the example by navigating to `http://localhost:8080/conference.html`

## Develop your own component

 1. Fork this repo
 2. Enhance the circuit-jsapi component with APIs you need from the [JS Client API](https://circuitsandbox.net/sdk/)
 4. Create your own amazing components
 5. Share them with the rest of us :)

