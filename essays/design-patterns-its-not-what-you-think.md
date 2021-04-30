---
layout: essay
type: essay
title: Design Patterns, It's Not What You Think
# All dates must be YYYY-MM-DD format!
date: 2021-04-29
labels:
  - Engineering
  - JavaScript
  - Design Patterns
  - Factory
  - Singleton
  - Model View Controller
---

<img class="ui xlarge image" src="../images/design-patterns.png" width="1000">

## Design Patterns, It's Not What You Think

<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp; Design patterns to a person who is outside the realm of software engineering would probably think that design patterns would probably have something to do with the design of a website in terms of aesthetics. I know this because prior to learning about design patterns my initial thought to seeing design patterns, I thought the same thing. I thought ok so i'm gonna learn maybe, the proper way to organize a website in terms that there is a unwritten code on how to properly layout a landing page, navigation bar, footer menu, or how to layout each new page that displays on the clients end. I was a few minutes into my learning and I kept waiting for the introduction on the assumptions that I had made instead I kept learning that a design pattern turns out it isn't what I assumed it to be, to my jaw dropped surprised.
</p>
<div style="text-align: justify">
&nbsp;&nbsp;&nbsp;&nbsp;Instead, it turns out that design patterns in software engineering  is a general, repeatable  to a commonly occurring problem in software design according to <a href="https://sourcemaking.com/design_patterns">Source Making</a>. In other words design patterns is a description on how to solve a problem that can be used in different situations. Design pattern was initially initiated by four authors Erich Gamma, Richard Helm, Ralph Johnson, and John Vlissides in 1994 they published a book titled "Design Patterns-Elements of Reusable Object-Oriented Software" and that is where the concept of design pattern started. In total there is about 23 known design patterns according to <a href="https://www.tutorialspoint.com/design_pattern/design_pattern_overview.htm">Tutorials Point</a> considering there are many of them, today we'll talk about the 3 most commonly used design patterns and how I incorporated these design patterns into my code.
</div>  

## The Four Commonly Used Design Patterns

### Singleton
<div style="text-align: justify">
  <p>
  &nbsp;&nbsp;&nbsp;&nbsp; The first design pattern is the Singleton Pattern, the gist of a Singleton pattern is a type of design that comes under the creational pattern and provides one of the best ways to create an object. In other words it provides a "global variable" in an object oriented language and that does not support global variables, and/or, provide complex global state. Some of the advantages in using the singleton design pattern is that it provides "global state" in an object-oriented manner; another advantage to a singleton design pattern is that it's a very easy design pattern to implement. Their are a couple of disadvantages when using the singleton pattern, those disadvantages is that it is not normally a thread-safe design and using a global state is normally not recommended.
  </p>
</div>  
  
### Publish-Subscribe Design Pattern (Observer)
<div style="text-align: justify">
  <p>
    &nbsp;&nbsp;&nbsp;&nbsp; The second design pattern we will be talking about is the Publish-Subscribe design pattern, a variation of Observer design pattern. According to <a href="https://en.wikipedia.org/wiki/Publish–subscribe_pattern">Wikipedia</a> publish-subscribe is a messaging pattern where senders of messages, called publishers, do not program the messages to be sent directly to specific receivers, called subscribers, but instead categorize published messages into classes without knowledge of which subscribes, if any, there maybe.
  </p>
  <p>
    &nbsp;&nbsp;&nbsp;&nbsp; The way I implemented this design pattern is through a class project that I had worked on during my time in college, in the project we were tasked in creating a site that would display all available food options with our school campus. In the site it would have a venues page which showed all available food establishments and a vendors page for a new vendor to login and be able to create their own vendor profile under the venues pages. The way I implemented the publish-subscribe scribe is by designating that when a user has logged in and if that user's role is a vendor the vendor option would show up, because the vendor was a subscriber to our set assignment role and is able to publish their establishment within the venues page. The example code can be seen below.
  </p>
</div>  
```js
  import { Vendors } from '../../api/vendor/Vendors';
  import { VendorTypes } from '../../api/vendor/VendorTypes';
  import { VendorClass } from '../../api/interests/vendorClassifications';
  
  /** Define a publication to publish all vendor classification. */
  Meteor.publish(VendorClass.userPublicationName, () => VendorClass.collection.find());
  
  /** Define a publication to publish all vendors. */
  Meteor.publish(Vendors.userPublicationName, () => Vendors.collection.find());
  
  /** Define a publication to publish this collection VendorTypes. */
  Meteor.publish(VendorTypes.userPublicationName, () => VendorTypes.collection.find());
  
  Meteor.publish(null, function () {
  if (this.userId) {
    return Meteor.roleAssignment.find({ 'user._id': this.userId });
  }
  return this.ready();
```
a sample code of the subscription to vendors is seen below.
```js
   this.userPublicationName = `${this.name}.publication.user`;
   this.adminPublicationName = `${this.name}.publication.admin`;
```

### Prototype Design Pattern
<div style="text-align: justify">
  <p>
    &nbsp;&nbsp;&nbsp;&nbsp;The last type of design pattern I will mention and talk about today is the prototype design pattern. A person would want to use the prototype design pattern to be able to build new instances from other instances. Any time a person uses Javascript or the class idea they are using an instance of the prototype design pattern. The way I incorporated the prototype design pattern in my codes is creating a class of venue, vendor, and vendorTypes which is used to encapsulate underlying Mongo collections and that is where prototype design pattern is used within my code. An Example code with the implementation of prototype design pattern can be seen below.
  </p>
</div>  
    
```js
  class VendorsCollection {
  constructor() {
    // The name of this collection.
    this.name = 'VendorsCollection';
    // Define the Mongo collection.
    this.collection = new Mongo.Collection(this.name);
    // Define the structure of each document in the collection.
    this.schema = new SimpleSchema({
      email: { type: String, index: true, unique: true },
      vendorName: { type: String, optional: true },
      campusLocation: { type: String, optional: true },
      vendorHours: { type: String, optional: true },
      description: { type: String, optional: true },
      picture: { type: String, optional: true },
    }, { tracker: Tracker });
    // Ensure collection documents obey schema.
    this.collection.attachSchema(this.schema);
    // Define names for publications and subscriptions
    this.userPublicationName = `${this.name}.publication.user`;
    this.adminPublicationName = `${this.name}.publication.admin`;
  }
}
```

## Concluding Remarks
<div style="text-align: justify">
  <p>
    &nbsp;&nbsp;&nbsp;&nbsp; As you can see, the design pattern isn't about the design or layout of how a website will look like nor is there unwritten code on how to organize a website as I initially thought it was. Design Pattern is nowhere related to design design, but rather a process in solving a repeatable problem with the same solutions over and over again. Some design patterns include prototype design pattern, publish-subscribe which is an instance of the observer design pattern, and singleton design pattern. The three design patterns mentioned above are just a few of the design patterns that I have so far used, I'm sure you may have encountered a design pattern in one way shape or form.
  </p>  
  
