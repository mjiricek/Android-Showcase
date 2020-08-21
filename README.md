# Android Architecture Showcase

## Description
Kotlin Android application that serves as showcase of a clean architecture. Among other things, provides a set of a guidelines, and demonstrates best practices.

This is a result of an iteration over different approaches we've been using in *Ahead iTec* apps.

## Basic concept
[The Clean Architecture](https://blog.cleancoder.com/uncle-bob/2012/08/13/the-clean-architecture.html) (**highly recommended to read**)

![Screenshots](art/Architecture.png?raw=true "Architecture diagram")

## Sample App

The app uses [Open Weather](https://openweathermap.org/api) API as it's remote endpoint.

### Project Structure

The project structure of the App module is **splitted by layer**

```
data
└───weather-feature
    │   mapper
    │   remote
    │   WeatherRepositoryImpl // Implementation of the contract [WeatherRepository interface] from the domain layer.
    │   ...
└───foo-feature
    │   ...
    │
domain
└───weather-feature
    │   model
    │   GetCurrentWeatherByLocation
    │   WeatherRepository // Domain contains the interfaces to the data, on how we store and access data.
    │   ...
└───location-feature
    │   ...
    │
infrastructure
└───location-feature
    │   mapper
    │   LocationRepositoryImpl
    │   ...
presentation
└───navigation // Classes used to navigate through the application.
    │   Navigator
└───presenter
    │   ...
    │
└───view
    │   ...
    │
```

## FAQ

* **How do I combine use cases (interactors)?**

Basically, there are two approaches to combining use cases: 
1. Combine the use cases in the presenter (so in the presentation layer)
2. Combine the use cases in another use case (domain layer)

In the CA all of the business logic goes into an use case and presenters are "dumb". Therefore I personally prefer the second approach.

See [GetCurrentWeatherByLocation](https://gitlab.monetplus.cz/mjiricek/android-showcase/blob/master/app/src/main/java/com/aheaditec/architectureshowcase/flows/domain/weather/GetCurrentWeatherByLocation.kt)

## Download Architecture Module [ ![Download](https://api.bintray.com/packages/ahead/Architecture/architecture/images/download.svg) ](https://bintray.com/ahead/Architecture/architecture/_latestVersion) 

```gradle
implementation "com.aheaditec.architecture:architecture:$libVersions.architecture"
```
## Download Functional Module [ ![Download](https://api.bintray.com/packages/ahead/Architecture/functional/images/download.svg) ](https://bintray.com/ahead/Architecture/functional/_latestVersion) 

```gradle
implementation "com.aheaditec.functional:functional:$libVersions.functional"
```

## License

Copyright 2020 AHEAD iTec, s.r.o

Permission to use, copy, modify, and/or distribute this software for any purpose with or without fee is hereby granted, provided that the above copyright notice and this permission notice appear in all copies.

There is NO WARRANTY for this software. See [LICENSE](LICENSE.md) for details.
