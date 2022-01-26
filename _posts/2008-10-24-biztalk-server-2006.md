---
layout: post
title: Biztalk Server 2006 - Multiple Activate Receives and Returning Soap Faults Oddit
date: 2008-10-24 12:07:00.000000000 +00:00
type: post
parent_id: '0'
published: true
password: ''
status: publish
categories: []
excerpt: Multiple Activate Receives and Returning Soap Faults Oddity...
tags: []

---


Imagine a scenario where you have an orchestration exposed as a web service that has two public ports. Each port accepts a message of the same type, but one port is used to send new messages, and the other is used to send update messages. The port type for the port has an access modifier of public, is a request-response port type, plus has a Fault message defined in addition to the request and response messages.

In the orchestration, you create a listen shape and then add two activatable receives - one on each branch with one pointing to the request message of the new port, and one to the request message of the update port. So far so good.

At this point you're going to want to create a couple of send shapes in order to send back either a request message or a fault message. However, as I've just discovered, there's a slight catch, and it is this:

You have configured a scope shape with an exception handler block in each of the listen branches.

You have it configured such that at the end of the scope you send back a response message and in the exception handler block you return a fault message for BizTalk to wrap in a SOAP exception and return to the client. This seems perfectly reasonable on the face of it. The problem occurs at compilation time.

The compiler basically barfs with must receive before sending a fault message on an implemented port. What? Well, I've certainly performed a receive before sending, so why is it complaining? If I move the send of the response after the end of the scope but still within the listen branch, then it now barfs with must receive before sending a message whose messagetype corresponds to a requestresponse operation on an implemented port.

It appears that it doesn't like having two send shapes where one may execute before the other, therefore nullifying the receive for the second send shape.

So, in order to get around this, you need to put the two send shapes (response and fault message sends) in either branch of a decision shape. So, at the end of the scope, set a flag to indicate success and in the exception handler set the same flag to indicate that a fault has occurred. Then, after the scope, create a decision shape to test the flag and either send the response or send the fault.

Just out of interest, I moved the decision down in the orchestration until it was after the end of the listen shape (that is, it wasn't directly in any of the branches of the listen shape, but just located 'after'). In this case I get both of the compiler errors detailed earlier which is quite interesting. Probably as a result of the fact that it could have been possible to exit the listen from another branch, thereby not executing the receive shape for which we're returning a response.