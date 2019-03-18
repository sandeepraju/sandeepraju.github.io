---
title: "Kotlin value types"
layout: post
date: 2019-03-17 01:23
headerImage: false
tag:
- dev
- kotlin
- programming
star: false
category: blog
author: sandeeprajup
description: Representing values with type safety in Kotlin
---

In theory, typed languages like Kotlin, Java, etc. provide strong type safety. Every variable, argument, parameter has a definitive type which prevents you from passing, say a `String` to an `Int` (unlike Python or Ruby) and this has made catching bugs and code refactoring a breeze.

Broadly, types can be thought of as some sort of contract applied on a variable which restricts the "kind" of data that can be stored in it. These contracts are very broad on purpose -- `Int` can store integer values, `String` can store string values, and so on. The language (or the type system) never dictates what you store in a given type -- which means, a variable storing a "user id" vs storing an "user name" is essentially the same as far as the type system is concerned.

This loss of contextual, semantic type information causes a lot of hard to trace bugs and brings back many problems existent in non-typed programming languages.

### Ostensible type safety

```kotlin
fun saveUser(userId: String, userName: String): Unit = ...

val userId = "5bn9gbAa9o"
val userName = "Jane Doe"

saveUser(userName, userId) // oops, swapped arguments!
```

### Ambiguity without explicit documentation

```kotlin
fun waitForSomething(interval: Long): Unit = ...

waitForSomething(4) // 4 mins? 4 hours?
```

### Hard to refactor

```kotlin
val apiKey = "mrpioxoboeitetf"

// How do we find all the places where the apiKey is being used?
fun fetchKeyValidity(key: String): Long = ...
fun fetchUserForKey(key: String): User = ...
fun generateToken(key: String): String = ...
```

### Verbose names

```kotlin
fun process(
    sourceQueueTopic: String,
    destinationQueueTopic: String
): Unit = ...
```

I'm sure every developer working on a relatively big and rapidly evolving codebase have come across something like this. When I faced this recently, I looked at Kotlin for answers. Thankfully, Kotlin provides various mechanisms to deal with some of these problems.

## Data classes

The first obvious way to solve this "contextual" type safety issue is by creating custom classes to wrap your data. The way to do this in Kotlin is by creating a data class

```kotlin
data class UserId(val value: String)

val userId = UserId("5bn9gbAa9o") // wrap your string with UserId class

fun fetchUserById(userId: UserId): User
```

Though this seems to make sense on a first, as you start working with it, you'll start to realize the downsides of this approach.


## Value Types


How typed languages become non-typed
    - examples with string
    - examples with long

What are the problems with this
    -  performance implication (auto boxing, etc)

There are multiple ways to deal with this problem each solving a subset of problems. Let's start with the first one:


## A note on type aliasing
