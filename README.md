# GUNJS-Starterkit
#### A collection of tools you need to run a local-first, decentralized graph database.
- Developer support
- What is GunJS?
- GunJS tools
- Quickstart
<br>

# Developer support

### For GunJS Wiki check https://github.com/amark/gun/wiki
### If you have any more questions hit the GunJS community https://gitter.im/amark/gun
<br>

### Need a hand? Artificial Intelligence Pair Programming
##### I work with ChatGPT for hours every day.
##### He writes me prototypes and POCs, and i just modify them myself.
##### It makes everything soo much easier. It's perfect for checking ideas right away. [See for yourself](https://www.youtube.com/watch?v=ng438SIXyW4&t=100s)
<br>

**Browser:** https://openai.com/blog/chatgpt/ <br>
**Desktop App (Win, Mac, Linux)** https://github.com/lencx/ChatGPT (installables at releases) <br>
<br>

# What is GunJS?
## GunJS GunDB Gun

##### GunJS can be explained as a decentralized alternative to cloud-based services like Dropbox and Firebase. Both Dropbox and Firebase provide cloud-based storage and synchronization of data, but with GunJS, the data is stored and synchronized across a decentralized network of peers, rather than relying on a central server. In this setup, each user's device acts as a node in the network, storing a copy of the data and making it available to other nodes. This means that data is always accessible, even if one node goes offline, because it can be retrieved from another node. GunJS also provides real-time synchronization, ensuring that all nodes in the network have the latest version of the data, similar to Dropbox and Firebase, but with the added benefits of improved security and privacy, as data is not controlled by a central authority. Additionally, GunJS allows for peer-to-peer data sharing, enabling users to directly exchange data without having to go through a central server. This makes it a flexible and scalable solution for real-time data storage and synchronization, similar to Firebase, but with a decentralized approach.<br>

## Peer-to-peer pubsub

##### Pubsub is an architecture where you subscribe to a “topic”, like “cats”, then whenever someone publishes a message of topic “cat”, you receive it. A peer-to-peer pubsub network means that anyone can publish, and anyone can subscribe.
<br>
<br>

![image](https://user-images.githubusercontent.com/67427045/216623143-a2144057-4d46-4318-b052-f435dc8a8990.png)
<br><br>

# GunJS Tools

## Gun, Desktop-Relay, Form, Relay Donation, Digital Globe (location-based services)
### https://github.com/amark/gun
#### An open source cybersecurity protocol for syncing decentralized graph data.

### https://github.com/worldpeaceenginelabs/ELECTRON-GUN
#### A Gun Relay Server executable for Desktop (Windows,-Linux,-MAC)

### https://github.com/worldpeaceenginelabs/FORM-GUN
#### A decentralized form handler with Gun for "static" JAMStack websites on a CDN. Plus "Svelte Compiler Tutorial with Gun"

### https://github.com/worldpeaceenginelabs/DONATE-DECENTRALIZE-UI
#### A little taskbar which empowers your fanbase to deploy a Gun relay on multiple ways to support your decentralized website/app.
 
### https://github.com/worldpeaceenginelabs/CESIUM-GUN
#### This is a POC of a decentralized, open-source Google Earth made with Gun and Cesium.<br>
<br>

## Storage logic

### GunJS - Included and third-party storage solutions https://github.com/amark/gun/wiki/Storage
#### To permanently store all GUN's data, your GUN server app must define which storage engine to use. By default a GUN server will store the data in a file, but this is just meant to be used during development. It is not a sound solution for production.
#### However, GUN is different to most other databases when it comes to dev vs prod setup in that the only distinction is that a production setup can maybe include a persistent storage option (e.g. AWS S3, IPFS...) for a participating relay peer. That's not mandatory though, browsers peers with their localStorage storage are sufficient more often than not, doesn't matter if you're still in development or already running your app in production with customers.<br>
<br>

## Webcrypto API
#### https://gist.github.com/pedrouid/b4056fd1f754918ddae86b32cf7d803e (Web Cryptography API Examples - A collection of well commented, well ordered snippets for 20 algorithms)
#### https://diafygi.github.io/webcrypto-examples/ (This table is live! Every ✓ or ✗ on this page is a test to see if your browser supports that method in WebCryptoAPI.)
#### God bless the internet, open-source and collaboration. Amen 🙏😂
<br>

## Authentication, encryption/hash, security
### https://github.com/worldpeaceenginelabs/GunJS-AUTH-SIGN-UP-LOGIN-LOGOUT
#### Gun-Auth - Ready to go sign-up, login, logout for the decentralized database GunJS.

### https://github.com/wuyanxin/totp.js
#### TOTP(Time-based one-time password) generator, support for Google Authenticator [Demo](https://wuyanxin.github.io/totp.js/demo/index.html)

### https://github.com/antelle/argon2-browser
#### Argon2 library compiled for browser runtime

### https://github.com/ai/nanoid
#### A tiny (130 bytes), secure, URL-friendly, unique string ID generator for JavaScript
 
### https://github.com/mozilla/node-srp
#### Secure Remote Password (SRP)<br>
<br>

# QUICKSTART
##### for components, apps, webapps, dapps... (the decentralized back-end)

## Table of contents
- GUN Relays
- Basic Principles
- Spaces
- Frozen Space = Content Addressing
- Comparing the graph structure to a folder system
- Fetching and storing data
- SEA (security, encryption, authentication)
- Understanding your GUN Relay
<br>

# GUN Relays
##### Gun works local first even without ever using a relay, but for syncing between clients you need a relay

### [Gun Relay (How to run a node - Deploy a GUN relay server everywhere on GUN WIKI)](https://github.com/amark/gun/wiki#how-to-run-a-node---deploy-a-gun-relay-server-everywhere)
### [Gun Relay Desktop (Electron Gun)](https://github.com/worldpeaceenginelabs/ELECTRON-GUN)
### [Gun Relay Donation Tool (Donate Decentralize UI)](https://github.com/worldpeaceenginelabs/DONATE-DECENTRALIZE-UI)<br>
<br>

# Basic Principles
##### .get() | .put | .on - There are [more methods...](https://gun.eco/docs/API)(API) but these three are the basic ones.

##### This is pretty much the core of everything. Notice how easy it is to connect your front-end code with the graph database GUN.
##### Notice that no matter how complex your function is: You just drop the result into one or multible variables and connect them to the GUN write function (green boxes, green lines).
##### Last, you can easily receive the data in any function, again, no matter how complex, by ```db.on(data => {//your function here});``` and get the data that you wrote to GUN before (red boxes, red lines)<br>
<br>

![image](https://user-images.githubusercontent.com/67427045/212865152-88544d46-f46b-4cd5-9d2e-4f2571dfb80b.png)
![image](https://user-images.githubusercontent.com/67427045/216111036-ee93b490-3506-42cf-a454-e416962b86d3.png)
##### This script saves a long/lat pair to the GUN graph, and renders a point on the globe, if the local clients graph (browser local storage) or a connected graph (GUN-Relay) receive a new entry.<br>
##### The ```.on(data)``` subscribes to the GUN graph. Everything's new to the graph will automatically be rendered on the globe. Both local storage graph and/or relay graph changes!
<br>

# Spaces

##### GUN supports more than just key/value pairs, it is a graph database that can store SQL-like tables, JSON-like documents, files and livestreaming video, plus relational and hypergraph data!
##### Beware! Anyone can edit the data by default - to fix this, we have to use the User system. GUN is a universal graph which has 3 logical "spaces" protected by SEA:
<br>

![image](https://user-images.githubusercontent.com/67427045/216807753-fa226fc1-7b62-4d3c-9df1-e5977f006b18.png)<br>
<br>

### Public Space
##### ```.get(name).put(data)``` https://gun.eco/docs/API

### Anyone can add, change, or remove data from here. Think of it as a giant wiki.
##### Note: Some data here may be encrypted such that the content stays secret, but it can always be overwritten. Imagine in real life someone hides a prize in a vault at the beach: Once it is found it may be damaged or moved, but only a person who knows the key can unlock it.
<br>

### User Space
##### ```user.get(name).put(data)``` https://gun.eco/docs/User

### (or Key Space) Only data signed with the user's key can be put. Uses SEA. This data can only be be changed, added or removed, by the owner. The data can be either private or publicly readable.
##### Note: Data is cryptographically owned by the user, there is no "app admin" or "website owner", this may change how you build apps but it guarantees better safety. Owners can authorize or give other users permission to edit the owner's data. Again, the owner does this, not the app developer or database admin.
<br>

# Frozen Space = Content Addressing
##### ```gun.get('#name').get(name).put(data);``` https://gun.eco/docs/Frozen

### (Hash Space, Content Id Space) The # operator is used. Gun interprets something like "Only allow data to be put here if its hash matches the appended hash object." This data cannot be changed or removed, only added to. Nobody owns this data.
##### Note: If nobody stores the data it may be forgotten, if the peers that store it are offline the data may not be found until they are online again. This is true of data in any space though.<br><br>

### Content Addressing (general explainer)
##### When data is added to a hash space, its contents are hashed using a cryptographic algorithm, producing a unique hash value. This hash value is then appended to the location in the content ID space where the data is being added.

##### Subsequently, if anyone wants to add more data to that same location, they must include the same hash value in their request. This ensures that only data with the correct hash value can be added to that location.

##### Once data is added to a hash space, it cannot be changed or removed. This means that the data is immutable and its contents remain fixed over time.

##### Nobody owns the data in a hash space, as it is stored in a decentralized and distributed network. This makes it difficult for any individual or entity to exert control over the data.

#####  Once you know the CID of a file on the network, you have all you need for the network to locate and return the file back to you. 
<br>

### Data can be in graphs that link across different spaces.
##### So don't assume data is only in one space! For instance, user data can point to public data which can be edited by anyone, just not the link itself. Likewise, public data could link to frozen or user data, but anyone could edit the link itself. One very powerful combination is frozen links to user data, nobody can edit the link but the data itself can be updated by the owner.<br>
<br>

![image](https://user-images.githubusercontent.com/67427045/219666590-b3e60857-2e4c-4d3e-a1c1-f70514569b8f.png)
<br>

##### Immutable links to mutable user content

##### Write
```javascript
// Logged in user writes a message in his signed graph. Notice, it should be an object in order to have a soul
gun.user().get('messages').set({text:'hello'}).on(async data => { store message in User Space then...
    let soul = data._["#"] // gets us the Soul of the just stored node !!!Gun.node.soul(data) is DEPRECATED!!! 
    let hash = await SEA.work(soul, null, null,{name:'SHA-256'}) // gets us the hash of the above data
    gun.get('#messages').get(hash).put(soul)  // User puts a hashed soul of the message in a public content-addressed node
})
```
##### Read
```javascript
// Others can read the message later with the soul
gun.get('#messages').map().on(data=> {
    gun.get(data).once((d=>console.log(d))) // {text:'hello'} 
})
```
<br>

# Comparing the graph structure to a folder system

![image](https://user-images.githubusercontent.com/67427045/219680043-de1cf0ee-ff0b-4f7a-9726-a58966197ca5.png)
<br><br>

### Allowed types
##### .put restricts the input to a specific subset:

- objects: partials, circular, and nested
- strings
- numbers
- booleans
- null
##### Note: Other values, like undefined, NaN, Infinity, arrays, will be rejected. ([Saving array in Gun](https://github.com/amark/gun/wiki/Snippets#saving-arrays-in-gun), but rather go for objects from the begin if possible)

### You cannot save primitive values at the root level.
```javascript
gun.put("oops"); // error
gun.get("odd").put("oops"); // error
```
##### You can circumvent this by specifying

```javascript
// Initialize GUN and tell it we will be storing all data local, and sync with relay http://localhost:8765/gun, and under the rootnode 'yourappname' in the graph...
var db = Gun(['http://localhost:8765/gun']).get('yourappname')

// ...then you can call the same content addresses as above without error
gun.put("oops"); // ok
gun.get("odd").put("oops"); // ok
```

##### btw: common is ```let gun = Gun();```, but no-brainer descriptions are preferable (what was Gun again?) ```let db = Gun();``` and then you can call your database like

```javascript
db.put("oops"); // ok
db.get("odd").put("oops"); // ok
```


### Saving objects
```javascript
gun.get('key').put({
  property: 'value',
  object: {
    nested: true
  }
})
```

### Saving primitives

```javascript
// strings
gun.get('person').get('name').put('Alice')

// numbers
gun.get('IoT').get('temperature').put(58.6)

// booleans
gun.get('player').get('alive').put(true)
```
<br>

# Fetching and storing data

##### So your references will basically look like this: ```.get(name).get(name)```
##### The following examples feature always the same reference, but handled with different methods:
<br>

### Fetching data

```javascript
.get(name).get(name).on(data) // subscribes to ```.get(name).get(name)``` in public space

user.get(name).get(name).on(data) //subscribes to ```.get(name).get(name)``` in user space

.get(name).get(name).once(data) // fetches ```.get(name).get(name)``` in public space once

user.get(name).get(name).once(data) // fetches ```.get(name).get(name)``` in user space once
```

##### Note: GUN is a functional reactive database for streaming event-driven data, gotta love/hate buzzwords - right? This means that .on subscribes to realtime updates, and may get called many times. Meanwhile .once grabs the data once, which is useful for procedural operations.
<br>

### Storing data

```javascript
.get(name).get(name).put(data) // store data in ```.get(name).get(name)``` in public space

user.get(name).get(name).put(data) //store data in ```.get(name).get(name)``` in user space
```
<br>

# SEA - Security, Encryption, & Authorization
### https://gun.eco/docs/SEA
<br>

### Sign-up, login, authentication, session management, and log-out
- When a user signs in or creates an account, their username and password are stored in the GUN database for recall.
- The Passphrase the user chooses will be extended with PBKDF2 to make it a secure way to login.
- When a user logs out, their session is terminated.
<br>

[Code here](https://github.com/worldpeaceenginelabs/GunJS-AUTH-SIGN-UP-LOGIN-LOGOUT)
![image](https://user-images.githubusercontent.com/67427045/216619993-5a2275cf-6b29-4799-9821-06b5dab69a36.png)
<br><br>

### Store data encrypted to User Space
##### This code encrypts the text 'secret text' with the user's public key using the Gun.SEA.encrypt method. The encrypted text is then stored in the user's private space using the db.user().get('encryptedText').put(encryptedText) method. NOTE: We need an authenticated (logged-in) user for this code to work.
![image](https://user-images.githubusercontent.com/67427045/216165080-53222ac5-ee5a-49a1-9704-e506366a1b25.png)
<br><br>

# Understanding your GUN Relay

### Question 1
##### ok so this sounds like a very complex setup to be decentralized and I dont want to have to pay for a bunch of relays I own myself. I highly doubt any of my customers would "donate" a relay. Wouldnt that mean it has to be always on? Or on a decent amount of the time? And all this wiping a relay and concern about security and encryption....makes me think GUN is not ready for production use

### Answer 1
##### I am actually about to go into my first production with my first Gun dapp, Couchsurfing Decentralized. Should be ready by the middle of the next week.

##### You say complex, but what does a centralized setup look like?
##### domain, dns provider, server

##### What does a decentralised setup look like?
##### domain, dns provider, relay

##### So not that different.
##### But full control, flexibility, speed(at least Gun), privacy, and endless potential because of the new possible design approachs. 

##### 😂 I hear that often first, but of course you need an incentive to activate your customer/user to donate a relay on, for instance, their desktop. A value could be a faster access due to your user hosting a relay for instance.

##### And no, relays do not have to be always on.

#####  Gun is a local first database which works out of the box even without a relay. Then just limited to its local graph and does not sync.
##### For your understanding: you could have a local app which's database is Gun and which runs years local without even ever connecting to a relay.

##### By experience a relay runs days, weeks, rather month, before it gets wiped, but I estimate the median lifetime of a relay to be a few hours to 48hours max. (just for my worst case calculations!)

##### In this time(few hours to 48h) we can sync the local graphs(databases) of our clients with no problem.

##### If the origin client of a piece of data is offline, the relays will continue to distribute the synced piece of data.

##### This means in practice, our piece of data is cached minimum a few hours, 48 hours, or even month.
##### And there is a high chance the user comes back within 48 hours, making the piece of data available to the relays again.

##### Now imagine all of your 10 relays get wiped at once.

##### After, the clients and the relays will start it's operation like nothing had happened before. So the relays start again to sync the local graphs of the clients to each other, based on the clients subscription/content-address ```gun.get(something).get(something).on(data)```

### Question 2
##### you say they have a lifetime of 48 hours max....how does that work? Does the relay server actually shut down?

### Answer 2
##### I say 48 hours max, only for my worst case calculations!
##### In reality you spin up a relay and it runs continously for weeks and month.

##### And its more about a reset which could cause a wipe, or a wipe causing a reset. Its not so much about relays would shut down(except in the following free tier example), they are stable, they run and they reset if necessary.

##### So almost Zero maintainence!

##### But possible:

- If its a free tier relay, with limitations, then it has maybe not 24h uptime, or gets wiped every x hours/days. (have minimum 3 of them at different free providers so they will balance each other out)
- You have no control over relays that you dont own. They could be wiped any time. (have minimum 3 foreign relays so they will balance each other out)
- Incentivised or "donated" desktop relays go on and off, new come, old go. (have minimum 3 donated relays so they will balance each other out.
##### Makes 9 individual "dangerous" relays, but if we would go for the following code, which combines all 9 of them, i promise you no problems at all. Thats decentralization at its best...

```javascript
// this code says all your Gun app client users initialize their Gun instance with all 9 relays at once.
var db = Gun(['https://relay1.com/gun, https://relay2.com/gun, https://relay3.com/gun, https://relay4.com/gun, https://relay5.com/gun, https://relay6.com/gun, https://relay7.com/gun, https://relay8.com/gun, https://relay9.com/gun,'])
```

>Incentivised or "donated" desktop relays go on and off, new come, old go. (have minimum 3 donated relays so they will balance each other out.

##### You could go for a script which fills the {drelays} variable at the begin of the following code from a list of donated relays. The criteria to add and delete relays from that list could be their monthly uptime.

```javascript
var drelays = relayUptimeFilter();

var db = Gun(['{drelays}, https://relay1.com/gun, https://relay2.com/gun, https://relay3.com/gun, https://relay4.com/gun, https://relay5.com/gun, https://relay6.com/gun'])
```

##### Same could actually work also for relays you dont own. Maybe have a bot crawling them all, and then filter.
