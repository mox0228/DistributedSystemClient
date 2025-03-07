# swagger-java-client

Ski Data API for NEU Seattle distributed systems course
- API version: 1.0.2
  - Build date: 2019-10-07T01:32:45.825Z[GMT]

An API for an emulation of skier managment system for RFID tagged lift tickets. Basis for CS6650 Assignments for 2019


*Automatically generated by the [Swagger Codegen](https://github.com/swagger-api/swagger-codegen)*


## Requirements

Building the API client library requires:
1. Java 1.7+
2. Maven/Gradle

## Installation

To install the API client library to your local Maven repository, simply execute:

```shell
mvn clean install
```

To deploy it to a remote Maven repository instead, configure the settings of the repository and execute:

```shell
mvn clean deploy
```

Refer to the [OSSRH Guide](http://central.sonatype.org/pages/ossrh-guide.html) for more information.

### Maven users

Add this dependency to your project's POM:

```xml
<dependency>
  <groupId>io.swagger</groupId>
  <artifactId>swagger-java-client</artifactId>
  <version>1.0.0</version>
  <scope>compile</scope>
</dependency>
```

### Gradle users

Add this dependency to your project's build file:

```groovy
compile "io.swagger:swagger-java-client:1.0.0"
```

### Others

At first generate the JAR by executing:

```shell
mvn clean package
```

Then manually install the following JARs:

* `target/swagger-java-client-1.0.0.jar`
* `target/lib/*.jar`

## Getting Started

Please follow the [installation](#installation) instruction and execute the following Java code:

```java
import io.swagger.client.*;
import io.swagger.client.auth.*;
import io.swagger.client.model.*;
import io.swagger.client.api.ResortsApi;

import java.io.File;
import java.util.*;

public class ResortsApiExample {

    public static void main(String[] args) {
        
        ResortsApi apiInstance = new ResortsApi();
        Body body = new Body(); // Body | Specify new Season value
        Integer resortID = 56; // Integer | ID of the resort of interest
        try {
            apiInstance.addSeason(body, resortID);
        } catch (ApiException e) {
            System.err.println("Exception when calling ResortsApi#addSeason");
            e.printStackTrace();
        }
    }
}
import io.swagger.client.*;
import io.swagger.client.auth.*;
import io.swagger.client.model.*;
import io.swagger.client.api.ResortsApi;

import java.io.File;
import java.util.*;

public class ResortsApiExample {

    public static void main(String[] args) {
        
        ResortsApi apiInstance = new ResortsApi();
        Integer resortID = 56; // Integer | ID of the resort of interest
        try {
            SeasonsList result = apiInstance.getResortSeasons(resortID);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling ResortsApi#getResortSeasons");
            e.printStackTrace();
        }
    }
}
import io.swagger.client.*;
import io.swagger.client.auth.*;
import io.swagger.client.model.*;
import io.swagger.client.api.ResortsApi;

import java.io.File;
import java.util.*;

public class ResortsApiExample {

    public static void main(String[] args) {
        
        ResortsApi apiInstance = new ResortsApi();
        try {
            ResortsList result = apiInstance.getResorts();
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling ResortsApi#getResorts");
            e.printStackTrace();
        }
    }
}
```

## Documentation for API Endpoints

All URIs are relative to */*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*ResortsApi* | [**addSeason**](docs/ResortsApi.md#addSeason) | **POST** /resorts/{resortID}/seasons | Add a new season for a resort
*ResortsApi* | [**getResortSeasons**](docs/ResortsApi.md#getResortSeasons) | **GET** /resorts/{resortID}/seasons | get a list of seasons for the specified resort
*ResortsApi* | [**getResorts**](docs/ResortsApi.md#getResorts) | **GET** /resorts | get a list of ski resorts in the database
*SkiersApi* | [**getSkierDayVertical**](docs/SkiersApi.md#getSkierDayVertical) | **GET** /skiers/{resortID}/seasons/{seasonID}/days/{dayID}/skiers/{skierID} | write a new lift ride for the skier
*SkiersApi* | [**getSkierResortTotals**](docs/SkiersApi.md#getSkierResortTotals) | **GET** /skiers/{skierID}/vertical | get the total vertical for the skier for specified seasons at the specified resort
*SkiersApi* | [**writeNewLiftRide**](docs/SkiersApi.md#writeNewLiftRide) | **POST** /skiers/{resortID}/seasons/{seasonID}/days/{dayID}/skiers/{skierID} | write a new lift ride for the skier

## Documentation for Models

 - [Body](docs/Body.md)
 - [LiftRide](docs/LiftRide.md)
 - [ResortsList](docs/ResortsList.md)
 - [ResortsListResorts](docs/ResortsListResorts.md)
 - [ResponseMsg](docs/ResponseMsg.md)
 - [SeasonsList](docs/SeasonsList.md)
 - [SkierVertical](docs/SkierVertical.md)
 - [SkierVerticalResorts](docs/SkierVerticalResorts.md)

## Documentation for Authorization

All endpoints do not require authorization.
Authentication schemes defined for the API:

## Recommendation

It's recommended to create an instance of `ApiClient` per thread in a multithreaded environment to avoid any potential issues.

## Author


