# <a href="http://microbean.org/"><img src="https://avatars0.githubusercontent.com/u/25515632?s=100&v=4"/><br/>microBean™</a>

At the intersection of Java, Kubernetes and the enterprise.

## Overview

The microBean suite of projects brings standards-based
component-oriented programming in Java to the Kubernetes ecosystem.

## Motivation

Java has been doing standards-defined component-oriented programming
for decades.  If you place your `.war` file within a Java
EE-compatible application server, you can use the standard components
it provides.

Such application servers are frequently (rightly or wrongly) seen as
bloated.  For those holding this view, they provide too many
components that do too many things.  You may need only one or two of
the dozen or so services they offer, but since Java EE is an
all-or-nothing bag of components the footprint of your application
together with the application server will be needlessly large.

Recently, MicroProfile has emerged in reaction to the all-or-nothing
Java EE approach.  It offers up a small grab bag of components that in
theory can be used together or apart.  You can use just MicroProfile
Config, for example, or MicroProfile Config and JAX-RS
together&mdash;hence "micro".

But implementations of MicroProfile to date are still following the
application server model.  You take delivery of a product that
"supports MicroProfile" (i.e. all of it) and you deploy your
application into it.  Components that you have no need of still come
along for the ride.

One of the foundational bits of MicroProfile is CDI (Contexts and
Dependency Injection).  CDI 2.0 enables a component-oriented
programming model, but does not require that any given component be
present.  It also standardizes the startup sequence and lifecycle for
a Java SE application, and allows plugins ("portable extensions") to
take part in that lifecycle.  Finally, it offers features like
interceptors, an event bus, dependency injection and object lifecycle
management.

The net effect is that a CDI 2.0 implementation functions as a
backplane to which components may attach themselves.

microBean fully embraces this philsophy by supplying interesting and
useful CDI components for your small, targeted application to use.
Many of these components are geared towards usage within Kubernetes.
For example, some components provide your application with a
Kubernetes client, preconfigured from standard sources.  Others offer
up Kubernetes events, allowing you to write your own controllers.
