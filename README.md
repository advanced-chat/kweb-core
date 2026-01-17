# Kweb - A Kotlin web framework

A fork of https://github.com/kwebio/kweb-core


## Quick Start

Read the [Introduction](https://docs.kweb.io/book/intro.html) or 
[Getting Started](https://docs.kweb.io/book/gettingstarted.html) from 
the [Kweb User Manual](https://docs.kweb.io/book/).

## Why another web framework?

Kweb is designed to make it easy for developers to create modern websites without having to worry about the complexities of communication between the server and the browser. With a unified codebase, you can focus on creating an intuitive and user-friendly interface, rather than spending time on technical details. By streamlining the development process, Kweb makes it easier to build functional and beautiful websites that meet the needs of your users.

## How does it work?

Kweb is a remote interface for a web browser's DOM (Document Object Model). With Kweb, you can create and manipulate DOM elements, and listen for and handle events, all using an intuitive Kotlin DSL that mirrors the structure of the HTML being created. Kweb is built on the Ktor framework, which handles HTTP, HTTPS, and WebSocket transport, and is optimized to minimize latency and resource usage on both the server and browser.

## Example
  
```kotlin
import kweb.*
import kweb.InputType.text

fun main() {
    Kweb(port = 16097) {
        doc.body {
            val name = kvar("")
            div {
                h1().text("Enter Your Name")
                input(type = text).value = name
            }
            div {
                span().text(name.map { "Hello, $it" })
            }
        }
    }
}

