---
layout: post
title: Domain Layer
source: [https://developer.android.com/jetpack/guide/domain-layer]
---

### Domain layer
Domain Layer is an optional layer between UI layer and Data layer

![domain layer](https://developer.android.com/topic/libraries/architecture/images/mad-arch-domain-overview.png)
>source: https://developer.android.com/topic/libraries/architecture/images/mad-arch-domain-overview.png]

Domain layer capsulizes complex business logic or simple basic reused by several ViewModel. It is not necessarily used for every apps. In case of resolving complexity or prefering reusability, Domain layer is needed.

#### Domain layer brings some advantages
- Prevent code duplication
- Improve readability of class using it
- Boost test possibility for app
- Prevent sizable class by disassemble responsibilities



