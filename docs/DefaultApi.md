# IO.Swagger.Api.DefaultApi

All URIs are relative to */*

Method | HTTP request | Description
------------- | ------------- | -------------
[**CreateLuggage**](DefaultApi.md#createluggage) | **POST** /luggage | Create a new luggage item
[**DeleteLuggage**](DefaultApi.md#deleteluggage) | **DELETE** /luggage/{luggageId} | Delete a luggage item
[**ExampleGet**](DefaultApi.md#exampleget) | **GET** /example | Server example operation
[**GetLuggageById**](DefaultApi.md#getluggagebyid) | **GET** /luggage/{luggageId} | Retrieve a luggage item by ID
[**ListLuggage**](DefaultApi.md#listluggage) | **GET** /luggage | List all luggage items
[**PingGet**](DefaultApi.md#pingget) | **GET** /ping | Server heartbeat operation
[**UpdateLuggage**](DefaultApi.md#updateluggage) | **PUT** /luggage/{luggageId} | Update a luggage item

<a name="createluggage"></a>
# **CreateLuggage**
> Luggage CreateLuggage (LuggageCreate body)

Create a new luggage item

Create a new luggage record in the system. Rate Limiting applies to this endpoint.

### Example
```csharp
using System;
using System.Diagnostics;
using IO.Swagger.Api;
using IO.Swagger.Client;
using IO.Swagger.Model;

namespace Example
{
    public class CreateLuggageExample
    {
        public void main()
        {
            // Configure OAuth2 access token for authorization: password
            Configuration.Default.AccessToken = "YOUR_ACCESS_TOKEN";

            var apiInstance = new DefaultApi();
            var body = new LuggageCreate(); // LuggageCreate | 

            try
            {
                // Create a new luggage item
                Luggage result = apiInstance.CreateLuggage(body);
                Debug.WriteLine(result);
            }
            catch (Exception e)
            {
                Debug.Print("Exception when calling DefaultApi.CreateLuggage: " + e.Message );
            }
        }
    }
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**LuggageCreate**](LuggageCreate.md)|  | 

### Return type

[**Luggage**](Luggage.md)

### Authorization

[password](../README.md#password)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)
<a name="deleteluggage"></a>
# **DeleteLuggage**
> void DeleteLuggage (string luggageId)

Delete a luggage item

Remove a luggage item from the system. Rate Limiting applies to this endpoint.

### Example
```csharp
using System;
using System.Diagnostics;
using IO.Swagger.Api;
using IO.Swagger.Client;
using IO.Swagger.Model;

namespace Example
{
    public class DeleteLuggageExample
    {
        public void main()
        {
            // Configure OAuth2 access token for authorization: password
            Configuration.Default.AccessToken = "YOUR_ACCESS_TOKEN";

            var apiInstance = new DefaultApi();
            var luggageId = luggageId_example;  // string | 

            try
            {
                // Delete a luggage item
                apiInstance.DeleteLuggage(luggageId);
            }
            catch (Exception e)
            {
                Debug.Print("Exception when calling DefaultApi.DeleteLuggage: " + e.Message );
            }
        }
    }
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **luggageId** | **string**|  | 

### Return type

void (empty response body)

### Authorization

[password](../README.md#password)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)
<a name="exampleget"></a>
# **ExampleGet**
> void ExampleGet ()

Server example operation

This is an example operation to show how security is applied to the call. Rate Limiting is enforced to protect the API.

### Example
```csharp
using System;
using System.Diagnostics;
using IO.Swagger.Api;
using IO.Swagger.Client;
using IO.Swagger.Model;

namespace Example
{
    public class ExampleGetExample
    {
        public void main()
        {
            // Configure OAuth2 access token for authorization: password
            Configuration.Default.AccessToken = "YOUR_ACCESS_TOKEN";

            var apiInstance = new DefaultApi();

            try
            {
                // Server example operation
                apiInstance.ExampleGet();
            }
            catch (Exception e)
            {
                Debug.Print("Exception when calling DefaultApi.ExampleGet: " + e.Message );
            }
        }
    }
}
```

### Parameters
This endpoint does not need any parameter.

### Return type

void (empty response body)

### Authorization

[password](../README.md#password)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)
<a name="getluggagebyid"></a>
# **GetLuggageById**
> Luggage GetLuggageById (string luggageId)

Retrieve a luggage item by ID

Get detailed information about a specific luggage item. Rate Limiting applies to this endpoint.

### Example
```csharp
using System;
using System.Diagnostics;
using IO.Swagger.Api;
using IO.Swagger.Client;
using IO.Swagger.Model;

namespace Example
{
    public class GetLuggageByIdExample
    {
        public void main()
        {
            // Configure OAuth2 access token for authorization: password
            Configuration.Default.AccessToken = "YOUR_ACCESS_TOKEN";

            var apiInstance = new DefaultApi();
            var luggageId = luggageId_example;  // string | 

            try
            {
                // Retrieve a luggage item by ID
                Luggage result = apiInstance.GetLuggageById(luggageId);
                Debug.WriteLine(result);
            }
            catch (Exception e)
            {
                Debug.Print("Exception when calling DefaultApi.GetLuggageById: " + e.Message );
            }
        }
    }
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **luggageId** | **string**|  | 

### Return type

[**Luggage**](Luggage.md)

### Authorization

[password](../README.md#password)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)
<a name="listluggage"></a>
# **ListLuggage**
> List<Luggage> ListLuggage ()

List all luggage items

Retrieve a list of all luggage items in the system. Rate Limiting applies to this endpoint.

### Example
```csharp
using System;
using System.Diagnostics;
using IO.Swagger.Api;
using IO.Swagger.Client;
using IO.Swagger.Model;

namespace Example
{
    public class ListLuggageExample
    {
        public void main()
        {
            // Configure OAuth2 access token for authorization: password
            Configuration.Default.AccessToken = "YOUR_ACCESS_TOKEN";

            var apiInstance = new DefaultApi();

            try
            {
                // List all luggage items
                List&lt;Luggage&gt; result = apiInstance.ListLuggage();
                Debug.WriteLine(result);
            }
            catch (Exception e)
            {
                Debug.Print("Exception when calling DefaultApi.ListLuggage: " + e.Message );
            }
        }
    }
}
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**List<Luggage>**](Luggage.md)

### Authorization

[password](../README.md#password)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)
<a name="pingget"></a>
# **PingGet**
> void PingGet ()

Server heartbeat operation

This operation shows how to override the global security defined above, as we want to open it up for all users. Rate Limiting is not applied here.

### Example
```csharp
using System;
using System.Diagnostics;
using IO.Swagger.Api;
using IO.Swagger.Client;
using IO.Swagger.Model;

namespace Example
{
    public class PingGetExample
    {
        public void main()
        {
            var apiInstance = new DefaultApi();

            try
            {
                // Server heartbeat operation
                apiInstance.PingGet();
            }
            catch (Exception e)
            {
                Debug.Print("Exception when calling DefaultApi.PingGet: " + e.Message );
            }
        }
    }
}
```

### Parameters
This endpoint does not need any parameter.

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)
<a name="updateluggage"></a>
# **UpdateLuggage**
> Luggage UpdateLuggage (LuggageUpdate body, string luggageId)

Update a luggage item

Update details of an existing luggage item. Rate Limiting applies to this endpoint.

### Example
```csharp
using System;
using System.Diagnostics;
using IO.Swagger.Api;
using IO.Swagger.Client;
using IO.Swagger.Model;

namespace Example
{
    public class UpdateLuggageExample
    {
        public void main()
        {
            // Configure OAuth2 access token for authorization: password
            Configuration.Default.AccessToken = "YOUR_ACCESS_TOKEN";

            var apiInstance = new DefaultApi();
            var body = new LuggageUpdate(); // LuggageUpdate | 
            var luggageId = luggageId_example;  // string | 

            try
            {
                // Update a luggage item
                Luggage result = apiInstance.UpdateLuggage(body, luggageId);
                Debug.WriteLine(result);
            }
            catch (Exception e)
            {
                Debug.Print("Exception when calling DefaultApi.UpdateLuggage: " + e.Message );
            }
        }
    }
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**LuggageUpdate**](LuggageUpdate.md)|  | 
 **luggageId** | **string**|  | 

### Return type

[**Luggage**](Luggage.md)

### Authorization

[password](../README.md#password)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)
