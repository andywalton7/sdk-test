---
title: PRO SDK
language_tabs:
  - csharp: C#
toc_footers: []
includes: []
search: false
highlight_theme: darkula
headingLevel: 2

---

<!-- Generator: Widdershins v3.6.6 -->

<h1 id="header">SortedPRO SDK Docs</h1>

Welcome to the SortedPRO SDK! Here you’ll find a brief overview of the SDK and what you can do with it.

If you just want to get integrating, check out the [Quick Start](https://pro-sdk-test.herokuapp.com/#sdk-quick-start) guide.

### In This Section

* [SDK Architecture](https://pro-sdk-test.herokuapp.com/#sdk-architecture)
* [Dependency Injection](https://pro-sdk-test.herokuapp.com/#dependency-injection)
* [Asynchronous Methods](https://pro-sdk-test.herokuapp.com/#asynchronous-methods)
* [API Docs](https://pro-sdk-test.herokuapp.com/#api-docs)

## SDK Architecture

The SortedPRO SDK is a .Net Standard 2.x library that enables you to use PRO's functionality in your applications. It is split into a series of services, of which each publishes its own data contracts and "mini-SDK". As such, you only need to reference the packages that you specifically require for your project, helping you to keep your dependency trees small.

### Service List

The full list of services in the SDK is:

* **[Consignments](https://www.nuget.org/packages/Sorted.PRO.SDK.Consignments/)** - Enables you to manage consignments, including creating, deleting, updating, and allocating to a carrier.
* **[Labels](https://www.nuget.org/packages/Sorted.PRO.SDK.Labels/)** - Enables you to get consignment and packages labels
* **[Orders](https://www.nuget.org/packages/Sorted.PRO.SDK.Orders/)** - Enables you to manage PRO orders, including, creating, deleting, updating, and packing into consignments,
* **[Quotes](https://www.nuget.org/packages/Sorted.PRO.SDK.Quotes/)** - Enables you to get quotes based on a consignment reference or specific details.
* **[Rates](https://www.nuget.org/packages/Sorted.PRO.SDK.Rates/)** - Enables you to reset the Rates cache.
* **[Reconciliation](https://www.nuget.org/packages/Sorted.PRO.SDK.Reconciliation/)** - Enables you to get a list of invoices for a particular customer
* **[Security](https://www.nuget.org/packages/Sorted.PRO.SDK.Security/)** - Enables you to manage user accounts and configure roles.
* **[Settings](https://www.nuget.org/packages/Sorted.PRO.SDK.Settings/)** - Enables you to administer your organisation's carriers, carrier services, collection calendars, packages sizes, service groups, and shipping locations.
* **[Shared](https://www.nuget.org/packages/Sorted.PRO.SDK.Shared/)** - Contains shared components used by all PRO mini-SDKs.
* **[Tracking](https://www.nuget.org/packages/Sorted.PRO.SDK.Tracking/)** - Enables you to get tracking events for your consignments.
* **[Webhooks](https://www.nuget.org/packages/Sorted.PRO.SDK.Webhooks/)** - Enables you to configure push tracking notifications via webhook.
* **[XmlValidation](https://www.nuget.org/packages/Sorted.PRO.SDK.XmlValidation/)** - Enables you to get the embedded XML schema.

When referencing a particular service, you must also reference its `DataTypes` (i.e. the data contract for that service) and `Interfaces`. For example, to use `Consignments` functionality you would need to reference the following:

* [Sorted.PRO.SDK.Consignments](https://www.nuget.org/packages/Sorted.PRO.SDK.Consignments/) 
* [Sorted.PRO.SDK.Interfaces.Consignments](https://www.nuget.org/packages/Sorted.PRO.SDK.Interfaces.Consignments/)
* [Sorted.PRO.SDK.DataTypes.Consignments](https://www.nuget.org/packages/Sorted.PRO.SDK.DataTypes.Consignments/)

Alternatively, you can reference the master package set, [Sorted.PRO.SDK](https://www.nuget.org/packages/Sorted.PRO.SDK/). This package set references all of PRO's "mini-SDKs", enabling you to consume the SDK with minimal package references and without requiring knowledge of the individual services.

### Common Dependencies

Many of the "mini-SDK" packages are dependent on a common SDK, which can be referenced at [Sorted.PRO.SDK.Shared](https://www.nuget.org/packages/Sorted.PRO.SDK.Shared/) and [Sorted.PRO.SDK.DataTypes.Common](https://www.nuget.org/packages/Sorted.PRO.SDK.DataTypes.Common/). See the SDK reference documentation for specific dependency information.

The following dependencies are common to almost all of the services in the PRO SDK. They are located in the [Sorted.PRO.SDK.Shared](https://www.nuget.org/packages/Sorted.PRO.SDK.Shared/) package:

* `ILogger` - Responsible for logging diagnostic information. Implementing `ILogger` enables you to connect to PRO's inbuilt logging. For example, you could provide an implementation that writes PRO logging messages into your own logging pipeline. Alternatively, you can use the provided `SdkReferenceLogger`, which logs to the console. 

* `IHttpClientFactory` - Responsible for efficient re-use of HTTP connections. The [Sorted.PRO.SDK.Shared](https://www.nuget.org/packages/Sorted.PRO.SDK.Shared/) package includes a default implementation called `HttpClientFactory`. We recommend that you use the provided implementation, rather than implementing this interface yourself. 

* `IEndpoints` - Enables you to specify the locations that the SDK sends HTTP requests to. For example, you might want to implementing `IEndpoints` yourself in order to have PRO send requests to your own internal systems for testing purposes. The SDK includes default implementations for production (`Production.Instance`) and sandbox (`Sandbox.Instance`) environments. 

## Dependency Injection

The PRO SDK is designed to be used with a dependency injection framework. All services have a corresponding interface, named with the `I{serviceName}` convention. For example, to create consignments you would use the `IConsignmentService` interface, which is in turn implemented by the concrete `ConsignmentService` class. 

## Asynchronous Methods 

The SDK includes both synchronous and asynchronous methods. We strongly recommend that you only utilise the asynchronous methods, as this will enable you to achieve far higher throughput on your own systems. The synchronous methods are only included to support scenarios where it is not possible for you to use asynchronous code, and will be deprecated in a future version of the SDK. 

## API Docs

For further information on PRO's APIs, see the [API Reference](https://docs.electioapp.com/#/api) and PRO Call Flow documentation.

# SDK Quick Start

Ready to get started with the SortedPRO SDK? This page explains how to set the SDK up and create a simple app to create, allocate, get labels for, and manifest a consignment.

This page is based on PRO's **Classic** workflow. For more information on this workflow, see the [PRO Call Flow](https://sorted-pro-flows-demo.herokuapp.com/#classic-flow) docs.

### On This Page

* [Sample Application](https://pro-sdk-test.herokuapp.com/#sample-application)
* [Downloading the SDK](https://pro-sdk-test.herokuapp.com/#downloading-the-sdk)
* [Configuration](https://pro-sdk-test.herokuapp.com/#configuration)
* [Creating a Consignment](https://pro-sdk-test.herokuapp.com/#creating-a-consignment)
* [Allocating a Consignment](https://pro-sdk-test.herokuapp.com/#allocating-a-consignment)
* [Getting Consignment Labels](https://pro-sdk-test.herokuapp.com/#getting-consignment-labels)
* [Manifesting a Consignment](https://pro-sdk-test.herokuapp.com/#manifesting-a-consignment)

## Sample Application

This guide is intended to be used in conjunction with the Classic Flow sample application, available from [LINK HERE]. This app shows the **Classic** PRO workflow implemented using the PRO SDK.

## Downloading the SDK

The PRO SDK is available as a collection of NuGet packages. For information on the specific packages you need for your project, see the SDK reference docs and the SDK Architecture section of the About the SDK page. 

Alternatively, you can reference the master package set, [Sorted.PRO.SDK](https://www.nuget.org/packages/Sorted.PRO.SDK/). This package set references all of PRO's "mini-SDKs", enabling you to consume the entire SDK with minimal package references and without requiring knowledge of its individual services.

<aside class= "info">
   For help on consuming packages from NuGet, see the <a href="https://docs.microsoft.com/en-us/nuget/consume-packages/overview-and-workflow">NuGet documentation</a>.
</aside>   

## Configuration

> Registering API Keys

```csharp
/// <summary>
/// Register the Sorted.PRO services
/// </summary>
/// <param name="configuration">The <see cref="IConfigurationRoot"/> used to get app configuration</param>
private void RegisterServices(IConfigurationRoot configuration)
{
    //using an extension method to register these services
    _container.RegisterApiKeyDependentService<IConsignmentService, ConsignmentService>(configuration);
    _container.RegisterApiKeyDependentService<IQuoteService, QuoteService>(configuration);
    _container.RegisterApiKeyDependentService<ILegacyLabelService, LegacyLabelService>(configuration);
    _container.RegisterApiKeyDependentService<IShippingLocationsService, ShippingLocationsServiceService>(configuration);
    _container.RegisterApiKeyDependentService<IConsignmentAllocationService, ConsignmentAllocationService>(configuration);
    _container.RegisterApiKeyDependentService<ICarrierServiceService, CarrierServiceService>(configuration);
    _container.RegisterApiKeyDependentService<ITrackingService, TrackingService>(configuration);
}
```

Many of the SDK's services require an `apiKey` as a dependency. The sample application demonstrates how to use an extension method to register those services that are dependent on an `apiKey`.

## Creating a Consignment

Many of PRO's key workflows require you to create a consignment object as an initial step. The `CreateConsignmentSample.cs` sample application file demonstrates how to create a consignment using the SDK.

In the PRO SDK, consignments are created by sending a `CreateConsignmentRequest` object to the [Create Consignment](https://docs.electioapp.com/#/api/CreateConsignment) endpoint via the `IConsignmentService.CreateConsignmentAsync(request)` method. The basic steps to create a consignment via the SDK are: 

> New IConsignmentService
```csharp
public class CreateConsignmentSample : ICreateConsignmentSample
{
   private readonly IConsignmentService _consignmentService;
   private readonly ISortedConfiguration _configuration;

   public CreateConsignmentSample(
      IConsignmentService consignmentService,
      ISortedConfiguration configuration)
   {
      _consignmentService = consignmentService;
      _configuration = configuration;
}
```
1. Create a new instance of the `IConsignmentService`. In the sample application, this is done via dependency injection.

> CreateConsignmentRequest
```csharp
public CreateConsignmentRequest BuildCreateConsignmentRequest(string postcode)
{   
   var createConsignmentRequest = new CreateConsignmentRequest
   {
      Direction = ConsignmentDirection.Outbound,
      Addresses = new List<Address> //all consignments must have at least 2 addresses
      {
            new Address
            {
               ShippingLocationReference = _configuration.ShippingLocationReference,
               AddressType = ConsignmentAddressType.Origin //must include an origin address
            },
            new Address
            {
               AddressType = ConsignmentAddressType.Destination, //must include a destination address
               AddressLine1 = "123 Some Street",
               Town = "Manchester",
               Region = "Greater Manchester",
               Postcode = postcode,
               Country = new Country("GB"),
               Contact = new Contact()
               {
                  Title = "Mr",
                  FirstName = "Tester",
                  LastName = "McTest",
                  Email = "tester.mctest@sorted.com",
                  Telephone = "0161123456"
               }
            }
      },
      Packages = new List<Package>
      {
            new Package
            {
               Weight = new Weight(1.5M),
               Dimensions = new Dimensions(10,10,10),
               Description = "A sample package",
               Value = new Money(new Currency("GBP"), 2.99M),
               PackageReferenceProvidedByCustomer = Guid.NewGuid().ToString()
            }
      },
      ConsignmentReferenceProvidedByCustomer = "my_reference"
   };

   return createConsignmentRequest;
}
```

2. Create a new `CreateConsignmentRequest`. This object contains the details of the consignment to be created. For details on the structure of the `CreateConsignmentRequest`, see SDK REFERENCE LINK HERE.
    The example to the right shows a simple consignment request for an outbound shipment containing a single package.

3. Use the `IConsignmentService.CreateConsignmentAsync(request)` method to pass the `CreateConsignmentRequest` to the [Create Consignment](https://docs.electioapp.com/#/api/CreateConsignment) API endpoint . PRO creates the consignment based on the details in the `CreateConsignmentRequest`and returns an `apiLink` detailing the consignment's reference and a link to the full consignment details.

> ExtractConsignmentReference
```csharp
private static string ExtractConsignmentReference(ApiLink apiLink)
{
   var href = apiLink.Href;
   var regex = new Regex("EC-[A-Z0-9]{3}-[A-Z0-9]{3}-[A-Z0-9]{3}$");
   var match = regex.Match(href);
   if (!match.Success)
   {
      throw new Exception($"Could not extract consignment reference from apiLink {href}");
   }

   return match.Value;
}
```

4. Extract the consignment reference from the API's response. PRO consignment references are a unique identifier for each consignment in the system, and have the format `EC-XXX-XXX-XXX`. The code sample to the right uses a regular expression to extract the consignment reference from the API's response.

## Allocating a Consignment

Once you've created a consignment, it must be allocated to a carrier service. PRO has multiple allocation endpoints, giving you the flexibility to allocate to carriers using whatever criteria suits you best. 

This example and the `AllocateConsignmentSample.cs` sample application file demonstrates how to allocate a consignment using the **Allocate With Default Rules** endpoint, which allocates the consignment to the cheapest service that meets your organisation's allocation rules. For more information on PRO's other allocation options, see the [API Reference](https://docs.electioapp.com/#/api/AllocateConsignment).

<aside class="note">
   In the context of SortedPRO, **allocation** is the process of selecting the carrier service that will be used to deliver the consignment.
</aside>   

In the PRO SDK, consignments can be allocated by passing a consignment reference to the [Allocate Consignment](https://docs.electioapp.com/#/api/AllocateConsignment) endpoint via the `IConsignmentAllocationService.AllocateConsignmentAsync(reference)` method. The basic steps to allocate a consignment via the SDK are: 

> Creating IAllocationService
```csharp
private readonly IConsignmentAllocationService _consignmentAllocationService;

public AllocateConsignmentSample(IConsignmentAllocationService consignmentAllocationService)
{
   _consignmentAllocationService = consignmentAllocationService;
}
```

1. Create a new instance of the `IConsignmentAllocationService`. In the sample application, this is done via dependency injection.

> AllocateConsignmentAsync method
```csharp
public async Task<AllocationSummary> AllocateConsignment(string consignmentReference)
{
   return await OperationHelper.Execute(async () =>
   {
      var allocationResult =
            await _consignmentAllocationService.AllocateConsignmentAsync(consignmentReference);
      JsonSampler.SummariseToJson(allocationResult);
      var first = allocationResult.FirstOrDefault();
      WriteAllocationSummary(first);
      return first;
   });
}
```  

2. Use the `IConsignmentAllocationService.AllocateConsignmentAsync(reference)` method to pass a consignment reference to the [Allocate Consignment](https://docs.electioapp.com/#/api/AllocateConsignment) API endpoint. 

    PRO allocates the consignment and returns an `AllocationSummary`, which contains links to the consignment resource that was allocated, a summary of the carrier service that the consignment was allocated to, a link to the relevant package labels, and a `ConsignmentLegs` array indicating how many legs the shipment will need.  

> Reading the AllocationSummary
```csharp
private static void WriteAllocationSummary(AllocationSummary summary)
{
   WriteProperty("Carrier name", summary.CarrierName);
   WriteProperty("Carrier reference", summary.CarrierReference);
   WriteProperty("Carrier service", summary.CarrierServiceName);
   WriteProperty("Carrier service reference", summary.CarrierServiceReference);
   WriteProperty("Description", summary.Description);
}

private static void WriteProperty(string property, string value)
{
   Console.WriteLine($"Property '{property}' has value '{value}'");
}
```
3. Read the `AllocationSummary` object to find the details of the carrier name, reference, service and service name.

Once allocated, the consignment's status changes to *Allocated*.

## Getting Consignment Labels

When a consignment is allocated, SortedPRO generates labels for each package in that consignment. The next step in the process is to retrieve those delivery labels. This example and the `GetLabelsSample.cs` sample application file demonstrates how to retrieve labels using the `LegacyLabelService`.

The basic steps to get consignment labels via the SDK are: 

> Creating ILegacyLabelService
```csharp
private readonly ILegacyLabelService _legacyLabelService;

public GetLabelsSample(ILegacyLabelService legacyLabelService)
{
   _legacyLabelService = legacyLabelService;
}
```

1. Create a new instance of the `ILegacyLabelService`. In the sample application, this is done via dependency injection.

> AllocateConsignmentAsync(reference, format) method
```csharp
public async Task GetLabels(string consignmentReference, bool open = true)
{
   await OperationHelper.Execute(async () =>
   {
      var labelData = await _legacyLabelService.GetLabelsAsync(consignmentReference, labelFormat);
      SummariseLabels(labelData);
      JsonSampler.SummariseToJson(labelData);
      if (open)
      {
            OpenLabel(labelData, consignmentReference);
      }
   });
}      
```

2. Use the `ConsignmentAllocationService.AllocateConsignmentAsync(reference, format)` method to pass a `consignmentReference` and (optionally) a `labelFormat` to the [Allocate Consignment](https://docs.electioapp.com/#/api/AllocateConsignment) API endpoint. 

    PRO returns a `GetLabelsResponse` containing all package labels associated with the specified consignment as a base64-encoded byte array in the format requested. 

> Saving the Label File
```csharp
private static string SaveFile(byte[] contents, string consignmentReference)
{
   try
   {
      var path = System.IO.Path.GetTempPath();
      var fileName = $"{Guid.NewGuid():N}-{consignmentReference}.pdf";
      var filePath = System.IO.Path.Combine(path, fileName);
      System.IO.File.WriteAllBytes(filePath, contents);
      return filePath;
   }
   catch (Exception e)
   {
      Console.WriteLine(e);
      throw;
   }
}    
```

3. Save the file to disk or to a remote location.

## Manifesting a Consignment

Once you've created a consignment, allocated it to a carrier service and printed labels for it, you're ready to manifest it. The `ManifestSample.cs` sample application file demonstrates how to manifest a consignment using the SDK.

<aside class="note">
   In the context of SortedPRO, the term "manifest" refers to advising the carrier that the consignment in question needs to be collected from the shipper.
</aside>   

In the PRO SDK, consignments are manifested by sending a `ManifestConsignmentsRequest` object to the [Manifest Consignments](https://docs.electioapp.com/#/api/ManifestConsignments) endpoint via the `IConsignmentService.ManifestConsignmentsAsync(request)` method. The basic steps to manifest a consignment via the SDK are:

> Creating IConsignmentService
```csharp
private readonly IConsignmentService _consignmentService;

public ManifestSample(IConsignmentService consignmentService)
{
   _consignmentService = consignmentService;
}
```

1. Create a new instance of `IConsignmentService`. In the sample application, this is done via dependency injection.

2. Construct a new `ManifestConsignmentsRequest`. This object contains the references of the consignments to be manifested. For details on the structure of the `ManifestConsignmentsRequest`, see LINK HERE.

> ManifestConsignmentsAsync(request) method
```csharp
public async Task ManifestConsignment(string consignmentReference)
{
   await OperationHelper.Execute(async () =>
   {
      var result = await _consignmentService.ManifestConsignmentsAsync(new ManifestConsignmentsRequest()
      {
            ConsignmentReferences = new List<string>
            {
               consignmentReference
            }
      });
      PrintResults(result);
      JsonSampler.SummariseToJson(result);
   });
```

3. Use the `IConsignmentService.ManifestConsignmentsAsync(request)` method to pass the `ManifestConsignmentsRequest` to the [Manifest Consignments](https://docs.electioapp.com/#/api/ManifestConsignments) endpoint.

    PRO attempts to manifest all of the consignments in the request, and returns a message indicating how many consignments could be manifested.

> Print Results
```csharp
private static void PrintResults(IEnumerable<WithMessage<string>> manifestResponse)
{
   foreach (var result in manifestResponse)
   {
      Console.WriteLine($"Manifested: {result.IsSuccess}. Message: {result.Message}");
   }
}
```

4. View the results of the operation.

We have only scratched the surface of what you can do with the PRO SDK in this tutorial. Read on to learn how to manage orders, quotes, and delivery options. 

# Use Cases

## Consumer Options

## Consumer Options Pickup

## Order Flex

## Consumer Options Flex

## Quotes

# SDK Reference