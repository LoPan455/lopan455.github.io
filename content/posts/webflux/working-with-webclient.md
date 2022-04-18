---
title: "Working with WebClient"
date: 2021-07-13T07:02:47-05:00
draft: false
---

WebClient is the reactive HTTP client that comes with the Spring Boot Reactive Web.
Like many Webflux components there is a bit of a learning curve to configuring and using the API.

Let's assume we have a WebClient instance configured as a clean and injected into a service class.

We can configure an instance of WebClient with a minimal configuration as a Spring Bean like this:

```kotlin
@Configuration
class MarvelApiConfig(
    @Value("\${marvel-api.base-url}") val baseUrl: String,
) {

    @Bean(name = ["marvelApiClient"])
    fun marvelApiClient(): WebClient  {
        return WebClient.create(baseUrl)
    }
}
```
A brief explanation of what's happening is here:

* The `MarvelApiConfig` class is marked as a Configuration class by the `@Configuration` annotation
* The Base URL for the downstream API is imported from the external `application-properties.yml` file
* A Bean is created with the name `marvelApiClient` that we can easily inject into other Spring-managed components
* We make a call to the `WebClient.create(url: String)` and return the resulting `WebClient` interface

This basic setup gives lets us inject this bean into our Service class like this example:
```kotlin
@Service
class ApiService(
    @Autowired val marvelApiClient: WebClient,
) {...}
```

Ok, we're all set to begin building the call we want to make to the downstream API.

