# BackscatterIO::Api

All URIs are relative to *https://api.backscatter.io/v0*

Method | HTTP request | Description
------------- | ------------- | -------------
[**enrich_asn**](Api.md#enrich_asn) | **GET** /enrichment/asn | enriches asn
[**enrich_ip**](Api.md#enrich_ip) | **GET** /enrichment/ip | enriches ip
[**enrich_network**](Api.md#enrich_network) | **GET** /enrichment/network | enriches network
[**hello**](Api.md#hello) | **GET** /hello | authenticate to the service
[**observations**](Api.md#observations) | **GET** /observations/{queryType} | fetches observations for a given ip address
[**trends**](Api.md#trends) | **GET** /trends/popular/{trendType} | Top N items


# **enrich_asn**
> ASNEnrichment enrich_asn(query)

enriches asn

returns enrichment data for an ASN

### Example
```ruby
# load the gem
require 'backscatterio'
# setup authorization
BackscatterIO.configure do |config|
  # Configure API key authorization: ApiKeyAuth
  config.api_key['X-API-KEY'] = 'YOUR API KEY'
  # Uncomment the following line to set a prefix for the API key, e.g. 'Bearer' (defaults to nil)
  #config.api_key_prefix['X-API-KEY'] = 'Bearer'
end

api_instance = BackscatterIO::Api.new

query = 'query_example' # String | 


begin
  #enriches asn
  result = api_instance.enrich_asn(query)
  p result
rescue BackscatterIO::ApiError => e
  puts "Exception when calling Api->enrich_asn: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **query** | **String**|  | 

### Return type

[**ASNEnrichment**](ASNEnrichment.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json



# **enrich_ip**
> IPEnrichment enrich_ip(query)

enriches ip

returns enrichment data for an ip

### Example
```ruby
# load the gem
require 'backscatterio'
# setup authorization
BackscatterIO.configure do |config|
  # Configure API key authorization: ApiKeyAuth
  config.api_key['X-API-KEY'] = 'YOUR API KEY'
  # Uncomment the following line to set a prefix for the API key, e.g. 'Bearer' (defaults to nil)
  #config.api_key_prefix['X-API-KEY'] = 'Bearer'
end

api_instance = BackscatterIO::Api.new

query = 'query_example' # String | 


begin
  #enriches ip
  result = api_instance.enrich_ip(query)
  p result
rescue BackscatterIO::ApiError => e
  puts "Exception when calling Api->enrich_ip: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **query** | **String**|  | 

### Return type

[**IPEnrichment**](IPEnrichment.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json



# **enrich_network**
> NetworkEnrichment enrich_network(query)

enriches network

returns enrichment data for a network

### Example
```ruby
# load the gem
require 'backscatterio'
# setup authorization
BackscatterIO.configure do |config|
  # Configure API key authorization: ApiKeyAuth
  config.api_key['X-API-KEY'] = 'YOUR API KEY'
  # Uncomment the following line to set a prefix for the API key, e.g. 'Bearer' (defaults to nil)
  #config.api_key_prefix['X-API-KEY'] = 'Bearer'
end

api_instance = BackscatterIO::Api.new

query = 'query_example' # String | 


begin
  #enriches network
  result = api_instance.enrich_network(query)
  p result
rescue BackscatterIO::ApiError => e
  puts "Exception when calling Api->enrich_network: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **query** | **String**|  | 

### Return type

[**NetworkEnrichment**](NetworkEnrichment.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json



# **hello**
> Hello hello

authenticate to the service

### Example
```ruby
# load the gem
require 'backscatterio'
# setup authorization
BackscatterIO.configure do |config|
  # Configure API key authorization: ApiKeyAuth
  config.api_key['X-API-KEY'] = 'YOUR API KEY'
  # Uncomment the following line to set a prefix for the API key, e.g. 'Bearer' (defaults to nil)
  #config.api_key_prefix['X-API-KEY'] = 'Bearer'
end

api_instance = BackscatterIO::Api.new

begin
  #authenticate to the service
  result = api_instance.hello
  p result
rescue BackscatterIO::ApiError => e
  puts "Exception when calling Api->hello: #{e}"
end
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**Hello**](Hello.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json



# **observations**
> Observations observations(query_type, query, opts)

fetches observations for a given ip address

### Example
```ruby
# load the gem
require 'backscatterio'
# setup authorization
BackscatterIO.configure do |config|
  # Configure API key authorization: ApiKeyAuth
  config.api_key['X-API-KEY'] = 'YOUR API KEY'
  # Uncomment the following line to set a prefix for the API key, e.g. 'Bearer' (defaults to nil)
  #config.api_key_prefix['X-API-KEY'] = 'Bearer'
end

api_instance = BackscatterIO::Api.new

query_type = 'query_type_example' # String | query type ip, network, asn, port, country

query = 'query_example' # String | ip address, cidr block, asn, port, or country

opts = { 
  scope: 'scope_example' # String | timeframe to search over, e.g., 1d, 7d
}

begin
  #fetches observations for a given ip address
  result = api_instance.observations(query_type, query, opts)
  p result
rescue BackscatterIO::ApiError => e
  puts "Exception when calling Api->observations: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **query_type** | **String**| query type ip, network, asn, port, country | 
 **query** | **String**| ip address, cidr block, asn, port, or country | 
 **scope** | **String**| timeframe to search over, e.g., 1d, 7d | [optional] 

### Return type

[**Observations**](Observations.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json



# **trends**
> Trends trends(trend_type, opts)

Top N items

A listing of the top N items observered over the query scope

### Example
```ruby
# load the gem
require 'backscatterio'
# setup authorization
BackscatterIO.configure do |config|
  # Configure API key authorization: ApiKeyAuth
  config.api_key['X-API-KEY'] = 'YOUR API KEY'
  # Uncomment the following line to set a prefix for the API key, e.g. 'Bearer' (defaults to nil)
  #config.api_key_prefix['X-API-KEY'] = 'Bearer'
end

api_instance = BackscatterIO::Api.new

trend_type = 'trend_type_example' # String | which item type you want to perform a trend over

opts = { 
  scope: 'scope_example' # String | timeframe to search over, e.g., 1d, 7d
}

begin
  #Top N items
  result = api_instance.trends(trend_type, opts)
  p result
rescue BackscatterIO::ApiError => e
  puts "Exception when calling Api->trends: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **trend_type** | **String**| which item type you want to perform a trend over | 
 **scope** | **String**| timeframe to search over, e.g., 1d, 7d | [optional] 

### Return type

[**Trends**](Trends.md)

### Authorization

[ApiKeyAuth](../README.md#ApiKeyAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json



